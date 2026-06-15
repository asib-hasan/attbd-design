<template>
  <section class="relative bg-primary-700 py-10 md:py-16 overflow-hidden">
    <!-- Grid pattern -->
    <div class="absolute inset-0 hero-grid opacity-20"></div>

    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Breadcrumb -->
      <nav class="flex items-center gap-2 text-sm text-white/50 mb-6">
        <NuxtLink to="/" class="hover:text-white/80 transition-colors">Home</NuxtLink>
        <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
          <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/>
        </svg>
        <span v-if="parent">
          <NuxtLink :to="parentTo" class="hover:text-white/80 transition-colors">{{ parent }}</NuxtLink>
          <svg class="w-3.5 h-3.5 inline-block mx-2" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/>
          </svg>
        </span>
        <span class="text-white/80 font-medium">{{ title }}</span>
      </nav>

      <!-- Label -->
      <div v-if="label" class="inline-flex items-center gap-2 px-3 py-1.5 bg-accent-500/15 text-accent-400 text-xs font-semibold rounded-full border border-accent-500/25 mb-4">
        {{ label }}
      </div>

      <h1 class="text-3xl md:text-5xl font-black uppercase text-white leading-tight mb-3 max-w-3xl">
        {{ title }}
      </h1>
      <p v-if="subtitle" class="text-lg text-white/60 max-w-2xl leading-relaxed">
        {{ subtitle }}
      </p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  subtitle?: string
  label?: string
  parent?: string
  parentTo?: string
}>()
</script>
