<template>
  <div>
    <PageHero
      title="Our Solutions"
      subtitle="Intelligent Transportation Systems tailored for Bangladesh's roads, bridges, ports and infrastructure — from concept through to long-term maintenance."
      label="ITS Solutions"
    />

    <section class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Intro -->
        <div class="max-w-3xl mx-auto text-center mb-14">
          <p class="text-slate-600 leading-relaxed text-lg">
            ITS (Intelligent Transportation Systems) is the use of advanced technology to enhance the operation of highway systems. The goal is to save lives, time, money, energy and the environment through computers, sensors, communications, and electronic devices.
          </p>
        </div>

        <!-- Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
          <ItemCard
            v-for="solution in solutions"
            :key="solution.slug"
            :to="'/solutions/toll-management'"
            :title="solution.title"
            :description="solution.shortDesc"
            :icon="solution.icon"
            :color="solution.color"
          />
        </div>
      </div>
    </section>


  </div>
</template>

<script setup lang="ts">
import { solutions } from '~/data/solutions'

useSeoMeta({
  title: 'Solutions — ATT | Intelligent Transportation Systems Bangladesh',
  description: 'Explore ATT\'s complete range of ITS solutions: toll collection, security, traffic monitoring, bridge safety, HTMS, customized software and more.',
})
</script>
