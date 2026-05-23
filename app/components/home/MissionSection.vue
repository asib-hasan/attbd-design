<template>
  <!-- Mission Section -->
  <section class="py-20 bg-slate-50 relative overflow-hidden">
    <div class="absolute top-0 right-0 w-80 h-80 bg-accent-500/5 rounded-full blur-3xl"></div>

    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <!-- Left -->
        <div>
          <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-accent-500/15 text-accent-400 text-xs font-semibold rounded-full border border-accent-500/25 mb-5">
            Our Purpose
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6 leading-tight">
            Leading Bangladesh's<br/>
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-accent-500 to-orange-400">Transportation Future</span>
          </h2>
          <p class="text-slate-600 leading-relaxed mb-6">
            To hold the leadership in Bangladesh by means of continuous strive in offering quality management for Operation & Maintenance of ETC of Roads & Highways.
          </p>
          <p class="text-slate-600 leading-relaxed mb-8">
            To become the market leader for Highways Systems Technology development in Bangladesh, leveraging cutting-edge ITS technologies.
          </p>
          <NuxtLink to="/about" class="inline-flex items-center gap-2 text-accent-400 font-semibold hover:gap-3 transition-all duration-200">
            Learn more about ATT
            <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
          </NuxtLink>
        </div>

        <!-- Right: Mission/Vision cards -->
        <div class="grid grid-cols-1 gap-5">
          <div v-for="card in cards" :key="card.title" class="bg-white shadow-xl shadow-slate-200/50 border border-slate-100 rounded-2xl p-6 hover:border-accent-500/30 transition-colors group">
            <div :class="['w-10 h-10 rounded-xl bg-gradient-to-br flex items-center justify-center text-white mb-4 shadow-md group-hover:scale-110 transition-transform', card.color]">
              <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" :d="card.icon" /></svg>
            </div>
            <h3 class="text-slate-900 font-bold text-lg mb-2">{{ card.title }}</h3>
            <p class="text-slate-500 text-sm leading-relaxed">{{ card.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const cards = [
  {
    title: 'Our Mission',
    text: 'Continuous quality improvement in the operation and maintenance of Electronic Toll Collection systems for Roads & Highways across Bangladesh.',
    color: 'from-blue-500 to-blue-700',
    icon: 'M15.59 14.37a6 6 0 01-5.84 7.38v-4.8m5.84-2.58a14.98 14.98 0 006.16-12.12A14.98 14.98 0 009.631 8.41m5.96 5.96a14.926 14.926 0 01-5.841 2.58m-.119-8.54a6 6 0 00-7.381 5.84h4.8m2.581-5.84a14.927 14.927 0 00-2.58 5.84m2.699 2.7c-.103.021-.207.041-.311.06a15.09 15.09 0 01-2.448-2.448 14.9 14.9 0 01.06-.312m-2.24 2.39a4.493 4.493 0 00-1.757 4.306 4.493 4.493 0 004.306-1.758M16.5 9a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0z',
  },
  {
    title: 'Our Vision',
    text: 'To become the undisputed market leader for Highways Systems Technology development in Bangladesh, setting regional standards for ITS excellence.',
    color: 'from-accent-500 to-orange-600',
    icon: 'M2.036 12.322a1.012 1.012 0 010-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178z M15 12a3 3 0 11-6 0 3 3 0 016 0z',
  },
]
</script>
