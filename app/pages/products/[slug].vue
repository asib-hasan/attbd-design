<template>
  <div v-if="product">
    <PageHero
      :title="product.title"
      :subtitle="product.shortDesc"
      label="Products"
      parent="Products"
      parent-to="/products"
    />

    <section class="py-12 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <!-- Back to List -->
        <NuxtLink to="/products" class="inline-flex items-center gap-2 text-sm font-semibold text-slate-500 hover:text-blue-600 mb-8 transition-colors">
          <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"/></svg>
          Back to List
        </NuxtLink>

        <div class="grid lg:grid-cols-12 gap-12 lg:gap-16 items-start">
          
          <!-- Image Column (Left Side) -->
          <div v-if="product.image" class="lg:col-span-5 lg:sticky lg:top-24 w-full aspect-[4/3] rounded-3xl overflow-hidden shadow-lg border border-slate-100">
            <img :src="product.image" :alt="product.title" class="w-full h-full object-cover" />
          </div>

          <!-- Content Column (Right Side) -->
          <div :class="product.image ? 'lg:col-span-7' : 'lg:col-span-12 max-w-4xl'">
            <!-- Icon + label -->
            <div class="flex items-center gap-4 mb-8">
              <div v-if="!product.image" :class="['w-16 h-16 rounded-2xl bg-gradient-to-br flex items-center justify-center text-white shadow-lg flex-shrink-0', product.color || 'from-slate-700 to-slate-900']">
                <component :is="iconComponent" :size="32" />
              </div>
              <div>
                <div class="text-xs font-semibold text-slate-400 uppercase tracking-wider">ATT Product</div>
                <h2 class="text-3xl md:text-4xl font-bold text-slate-900">{{ product.title }}</h2>
              </div>
            </div>

            <!-- Dynamic Content (from Summernote) -->
            <div v-if="product.content" class="prose prose-slate max-w-none prose-lg mb-10" v-html="product.content"></div>

            <!-- Fallback for current static data -->
            <template v-else>
              <p class="text-slate-600 leading-relaxed text-lg mb-10">{{ product.description }}</p>

              <!-- Specs -->
              <div class="bg-slate-50 rounded-2xl p-8 mb-8">
                <h3 class="text-lg font-bold text-slate-900 mb-6 flex items-center gap-2">
                  <svg class="w-5 h-5 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12h3.75M9 15h3.75M9 18h3.75m3 .75H18a2.25 2.25 0 002.25-2.25V6.108c0-1.135-.845-2.098-1.976-2.192a48.424 48.424 0 00-1.123-.08m-5.801 0c-.065.21-.1.433-.1.664 0 .414.336.75.75.75h4.5a.75.75 0 00.75-.75 2.25 2.25 0 00-.1-.664m-5.8 0A2.251 2.251 0 0113.5 2.25H15c1.012 0 1.867.668 2.15 1.586m-5.8 0c-.376.023-.75.05-1.124.08C9.095 4.01 8.25 4.973 8.25 6.108V8.25m0 0H4.875c-.621 0-1.125.504-1.125 1.125v11.25c0 .621.504 1.125 1.125 1.125h9.75c.621 0 1.125-.504 1.125-1.125V9.375c0-.621-.504-1.125-1.125-1.125H8.25zM6.75 12h.008v.008H6.75V12zm0 3h.008v.008H6.75V15zm0 3h.008v.008H6.75V18z"/></svg>
                  Technical Specifications
                </h3>
                <div class="grid sm:grid-cols-2 gap-3">
                  <div v-for="spec in product.specs" :key="spec" class="flex items-start gap-3 bg-white rounded-xl p-4 border border-slate-100">
                    <svg class="w-4 h-4 text-blue-500 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5"/></svg>
                    <span class="text-sm text-slate-700">{{ spec }}</span>
                  </div>
                </div>
              </div>

              <!-- Applications -->
              <div class="bg-blue-50 rounded-2xl p-8">
                <h3 class="text-lg font-bold text-slate-900 mb-5 flex items-center gap-2">
                  <svg class="w-5 h-5 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M3.75 12h16.5m-16.5 3.75h16.5M3.75 19.5h16.5M5.625 4.5h12.75a1.875 1.875 0 010 3.75H5.625a1.875 1.875 0 010-3.75z"/></svg>
                  Typical Applications
                </h3>
                <div class="flex flex-wrap gap-3">
                  <span v-for="app in product.applications" :key="app" class="px-4 py-2 bg-white text-blue-700 text-sm font-medium rounded-xl border border-blue-100 shadow-sm">
                    {{ app }}
                  </span>
                </div>
              </div>
            </template>
          </div>
        </div>
      </div>
    </section>
  </div>

  <div v-else class="min-h-screen flex items-center justify-center text-center px-4">
    <div>
      <div class="text-6xl font-black text-slate-200 mb-4">404</div>
      <h1 class="text-2xl font-bold text-slate-800 mb-3">Product Not Found</h1>
      <NuxtLink to="/products" class="px-6 py-3 bg-primary-700 text-white font-semibold rounded-xl">Back to Products</NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
import * as icons from '@lucide/vue'
import { products } from '~/data/products'

const route = useRoute()
const slug = computed(() => route.params.slug as string)
const product = computed(() => products.find(p => p.slug === slug.value))
const otherProducts = computed(() => products.filter(p => p.slug !== slug.value))
const iconComponent = computed(() => (icons as any)[product.value?.icon ?? 'Activity'] || icons.Activity)

useSeoMeta({
  title: computed(() => product.value ? `${product.value.title} — ATT Products` : 'Product Not Found'),
  description: computed(() => product.value?.shortDesc ?? ''),
})
</script>
