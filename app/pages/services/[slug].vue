<template>
  <div v-if="service">
    <PageHero
      :title="service.title"
      :subtitle="service.shortDesc"
      label="Services"
      parent="Services"
      parent-to="/services"
    />

    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">
          <!-- Main -->
          <div class="lg:col-span-2">
            <div class="flex items-center gap-4 mb-8">
              <div :class="['w-16 h-16 rounded-2xl bg-gradient-to-br flex items-center justify-center text-white shadow-lg', service.color]">
                <component :is="iconComponent" :size="32" />
              </div>
              <div>
                <div class="text-xs font-semibold text-slate-400 uppercase tracking-wider">ATT Service</div>
                <h2 class="text-xl font-bold text-slate-900">{{ service.title }}</h2>
              </div>
            </div>

            <p class="text-slate-600 leading-relaxed text-lg mb-10">{{ service.description }}</p>

            <!-- Highlights -->
            <div class="bg-slate-50 rounded-2xl p-8">
              <h3 class="text-lg font-bold text-slate-900 mb-6 flex items-center gap-2">
                <svg class="w-5 h-5 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 011.04 0l2.125 5.111a.563.563 0 00.475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 00-.182.557l1.285 5.385a.562.562 0 01-.84.61l-4.725-2.885a.563.563 0 00-.586 0L6.982 20.54a.562.562 0 01-.84-.61l1.285-5.386a.562.562 0 00-.182-.557l-4.204-3.602a.562.562 0 01.321-.988l5.518-.442a.563.563 0 00.475-.345L11.48 3.5z"/></svg>
                Service Highlights
              </h3>
              <div class="grid sm:grid-cols-2 gap-3">
                <div v-for="h in service.highlights" :key="h" class="flex items-start gap-3 bg-white rounded-xl p-4 border border-slate-100">
                  <svg class="w-4 h-4 text-green-500 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5"/></svg>
                  <span class="text-sm text-slate-700 font-medium">{{ h }}</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Sidebar -->
          <div class="space-y-6">
            <div class="bg-gradient-to-br from-primary-900 to-primary-700 rounded-2xl p-8 text-white">
              <h3 class="font-bold text-xl mb-3">Discuss Your Requirements</h3>
              <p class="text-white/60 text-sm mb-6 leading-relaxed">Our service team is ready to create a tailored plan for your project needs.</p>
              <NuxtLink to="/contact" class="block text-center px-5 py-3 bg-accent-500 hover:bg-accent-600 text-white font-semibold rounded-xl transition-all hover:scale-105 text-sm mb-3">
                Contact Us Now
              </NuxtLink>
              <a href="tel:+88-2-8832313" class="block text-center px-5 py-3 border border-white/20 text-white text-sm font-medium rounded-xl hover:bg-white/10 transition-colors">
                +88-2-8832313
              </a>
            </div>

            <div class="bg-slate-50 rounded-2xl p-6">
              <h4 class="font-bold text-slate-900 mb-4 text-sm">Other Services</h4>
              <div class="space-y-2">
                <NuxtLink
                  v-for="s in otherServices"
                  :key="s.slug"
                  :to="`/services/${s.slug}`"
                  class="flex items-center gap-3 p-3 rounded-xl hover:bg-white hover:shadow-sm transition-all text-sm text-slate-600 hover:text-blue-700 group"
                >
                  <svg class="w-3.5 h-3.5 text-slate-300 group-hover:text-blue-500 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/></svg>
                  {{ s.title }}
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Related services -->
    <section class="py-14 bg-slate-50 border-t border-slate-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-xl font-bold text-slate-900">More Services</h2>
          <NuxtLink to="/services" class="text-sm text-blue-600 font-semibold hover:underline flex items-center gap-1">
            View all
            <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
          </NuxtLink>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
          <ItemCard
            v-for="s in otherServices.slice(0, 3)"
            :key="s.slug"
            :to="`/services/${s.slug}`"
            :title="s.title"
            :description="s.shortDesc"
            :icon="s.icon"
            :color="s.color"
            cta="View service"
          />
        </div>
      </div>
    </section>
  </div>

  <div v-else class="min-h-screen flex items-center justify-center text-center px-4">
    <div>
      <div class="text-6xl font-black text-slate-200 mb-4">404</div>
      <h1 class="text-2xl font-bold text-slate-800 mb-3">Service Not Found</h1>
      <NuxtLink to="/services" class="px-6 py-3 bg-primary-700 text-white font-semibold rounded-xl">Back to Services</NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
import * as icons from '@lucide/vue'
import { services } from '~/data/services'

const route = useRoute()
const slug = computed(() => route.params.slug as string)
const service = computed(() => services.find(s => s.slug === slug.value))
const otherServices = computed(() => services.filter(s => s.slug !== slug.value))
const iconComponent = computed(() => (icons as any)[service.value?.icon ?? 'Wrench'] || icons.Wrench)

useSeoMeta({
  title: computed(() => service.value ? `${service.value.title} — ATT Services` : 'Service Not Found'),
  description: computed(() => service.value?.shortDesc ?? ''),
})
</script>
