<template>
  <div v-if="solution">
    <PageHero
      :title="solution.title"
      :subtitle="solution.shortDesc"
      label="Solutions"
      parent="Solutions"
      parent-to="/solutions"
    />

    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">
          <!-- Main content -->
          <div class="lg:col-span-2">
            <!-- Icon + label -->
            <div class="flex items-center gap-4 mb-8">
              <div :class="['w-16 h-16 rounded-2xl bg-gradient-to-br flex items-center justify-center text-white shadow-lg', solution.color]">
                <component :is="iconComponent" :size="32" />
              </div>
              <div>
                <div class="text-xs font-semibold text-slate-400 uppercase tracking-wider">ATT Solution</div>
                <h2 class="text-xl font-bold text-slate-900">{{ solution.title }}</h2>
              </div>
            </div>

            <!-- Description -->
            <div class="prose prose-slate max-w-none mb-10">
              <p class="text-slate-600 leading-relaxed text-lg">{{ solution.description }}</p>
            </div>

            <!-- Features -->
            <div class="bg-slate-50 rounded-2xl p-8">
              <h3 class="text-lg font-bold text-slate-900 mb-6 flex items-center gap-2">
                <svg class="w-5 h-5 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                Key Features & Capabilities
              </h3>
              <div class="grid sm:grid-cols-2 gap-3">
                <div v-for="feature in solution.features" :key="feature" class="flex items-start gap-3 bg-white rounded-xl p-4 border border-slate-100">
                  <svg class="w-4 h-4 text-green-500 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5"/></svg>
                  <span class="text-sm text-slate-700 font-medium">{{ feature }}</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Sidebar -->
          <div class="space-y-6">
            <!-- CTA Card -->
            <div class="bg-gradient-to-br from-primary-900 to-primary-700 rounded-2xl p-8 text-white">
              <h3 class="font-bold text-xl mb-3">Interested in this solution?</h3>
              <p class="text-white/60 text-sm mb-6 leading-relaxed">Our experts are ready to discuss your specific requirements and provide a tailored proposal.</p>
              <NuxtLink to="/contact" class="block text-center px-5 py-3 bg-accent-500 hover:bg-accent-600 text-white font-semibold rounded-xl transition-all duration-200 hover:scale-105 text-sm mb-3">
                Get a Free Consultation
              </NuxtLink>
              <a href="tel:+88-2-8832313" class="block text-center px-5 py-3 border border-white/20 text-white text-sm font-medium rounded-xl hover:bg-white/10 transition-colors">
                +88-2-8832313
              </a>
            </div>

            <!-- Other Solutions -->
            <div class="bg-slate-50 rounded-2xl p-6">
              <h4 class="font-bold text-slate-900 mb-4 text-sm">Other Solutions</h4>
              <div class="space-y-2">
                <NuxtLink
                  v-for="s in otherSolutions"
                  :key="s.slug"
                  :to="`/solutions/${s.slug}`"
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

    <!-- Related: other solutions row -->
    <section class="py-14 bg-slate-50 border-t border-slate-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-xl font-bold text-slate-900">Explore More Solutions</h2>
          <NuxtLink to="/solutions" class="text-sm text-blue-600 font-semibold hover:underline flex items-center gap-1">
            View all
            <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
          </NuxtLink>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
          <ItemCard
            v-for="s in otherSolutions.slice(0, 3)"
            :key="s.slug"
            :to="`/solutions/${s.slug}`"
            :title="s.title"
            :description="s.shortDesc"
            :icon="s.icon"
            :color="s.color"
          />
        </div>
      </div>
    </section>
  </div>

  <!-- 404 state -->
  <div v-else class="min-h-screen flex items-center justify-center text-center px-4">
    <div>
      <div class="text-6xl font-black text-slate-200 mb-4">404</div>
      <h1 class="text-2xl font-bold text-slate-800 mb-3">Solution Not Found</h1>
      <p class="text-slate-500 mb-6">The solution you're looking for doesn't exist.</p>
      <NuxtLink to="/solutions" class="px-6 py-3 bg-primary-700 text-white font-semibold rounded-xl">Back to Solutions</NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
import * as icons from '@lucide/vue'
import { solutions } from '~/data/solutions'

const route = useRoute()
const slug = computed(() => route.params.slug as string)
const solution = computed(() => solutions.find(s => s.slug === slug.value))
const otherSolutions = computed(() => solutions.filter(s => s.slug !== slug.value))
const iconComponent = computed(() => (icons as any)[solution.value?.icon ?? 'Activity'] || icons.Activity)

useSeoMeta({
  title: computed(() => solution.value ? `${solution.value.title} — ATT Solutions` : 'Solution Not Found'),
  description: computed(() => solution.value?.shortDesc ?? ''),
})

// 404 if not found
if (!solution.value && import.meta.server) {
  throw createError({ statusCode: 404, message: 'Solution not found' })
}
</script>
