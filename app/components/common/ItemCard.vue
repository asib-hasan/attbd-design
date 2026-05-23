<template>
  <NuxtLink
    :to="to"
    class="group relative flex flex-col bg-white rounded-2xl border border-slate-100 overflow-hidden hover:shadow-2xl hover:-translate-y-1.5 transition-all duration-300"
  >
    <!-- Top color bar -->
    <div :class="['h-1.5 w-full bg-gradient-to-r', color]"></div>

    <div class="p-6 flex flex-col flex-1">
      <!-- Icon -->
      <div :class="['w-12 h-12 rounded-xl flex items-center justify-center mb-4 bg-gradient-to-br text-white shadow-lg', color]">
        <component :is="iconComponent" :size="24" />
      </div>

      <h3 class="font-bold text-lg text-slate-900 mb-2 group-hover:text-blue-700 transition-colors leading-snug">
        {{ title }}
      </h3>
      <p class="text-sm text-slate-500 leading-relaxed flex-1">{{ description }}</p>

      <!-- CTA -->
      <div class="flex items-center gap-1.5 mt-5 text-sm font-semibold text-blue-600 group-hover:gap-3 transition-all duration-200">
        {{ ctaText }}
        <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
          <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/>
        </svg>
      </div>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
import * as icons from '@lucide/vue'

const props = defineProps<{
  to: string
  title: string
  description: string
  icon: string
  color: string
  cta?: string
}>()

const iconComponent = computed(() => (icons as any)[props.icon] || icons.Activity)
const ctaText = computed(() => props.cta || 'Learn more')
</script>
