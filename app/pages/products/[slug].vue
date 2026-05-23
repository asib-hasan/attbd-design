<template>
  <div v-if="product">
    <PageHero
      :title="product.title"
      :subtitle="product.shortDesc"
      label="Products"
      parent="Products"
      parent-to="/products"
    />

    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">
          <!-- Main -->
          <div class="lg:col-span-2">
            <div class="flex items-center gap-4 mb-8">
              <div :class="['w-16 h-16 rounded-2xl bg-gradient-to-br flex items-center justify-center text-white shadow-lg', product.color]">
                <component :is="iconComponent" :size="32" />
              </div>
              <div>
                <div class="text-xs font-semibold text-slate-400 uppercase tracking-wider">ATT Product</div>
                <h2 class="text-xl font-bold text-slate-900">{{ product.title }}</h2>
              </div>
            </div>

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
          </div>

          <!-- Sidebar -->
          <div class="space-y-6">
            <div class="bg-gradient-to-br from-primary-900 to-primary-700 rounded-2xl p-8 text-white">
              <h3 class="font-bold text-xl mb-3">Request a Quote</h3>
              <p class="text-white/60 text-sm mb-6 leading-relaxed">Contact our product specialists for pricing, availability, and technical support.</p>
              <NuxtLink to="/contact" class="block text-center px-5 py-3 bg-accent-500 hover:bg-accent-600 text-white font-semibold rounded-xl transition-all hover:scale-105 text-sm mb-3">
                Request a Quote
              </NuxtLink>
              <a href="mailto:info@att-bd.com" class="block text-center px-5 py-3 border border-white/20 text-white text-sm font-medium rounded-xl hover:bg-white/10 transition-colors">
                info@att-bd.com
              </a>
            </div>

            <div class="bg-slate-50 rounded-2xl p-6">
              <h4 class="font-bold text-slate-900 mb-4 text-sm">Other Products</h4>
              <div class="space-y-2">
                <NuxtLink
                  v-for="p in otherProducts.slice(0, 6)"
                  :key="p.slug"
                  :to="`/products/${p.slug}`"
                  class="flex items-center gap-3 p-3 rounded-xl hover:bg-white hover:shadow-sm transition-all text-sm text-slate-600 hover:text-blue-700 group"
                >
                  <svg class="w-3.5 h-3.5 text-slate-300 group-hover:text-blue-500 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/></svg>
                  {{ p.title }}
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-14 bg-slate-50 border-t border-slate-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-xl font-bold text-slate-900">More Products</h2>
          <NuxtLink to="/products" class="text-sm text-blue-600 font-semibold hover:underline flex items-center gap-1">
            View all
            <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
          </NuxtLink>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
          <ItemCard
            v-for="p in otherProducts.slice(0, 3)"
            :key="p.slug"
            :to="`/products/${p.slug}`"
            :title="p.title"
            :description="p.shortDesc"
            :icon="p.icon"
            :color="p.color"
            cta="View product"
          />
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
