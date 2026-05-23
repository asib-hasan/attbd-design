<template>
  <div>
    <PageHero
      title="Our Services"
      subtitle="Professional installation, maintenance, consultancy, and shipping services — delivering complete lifecycle support for your infrastructure investments."
      label="Services"
    />

    <section class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <ItemCard
            v-for="service in services"
            :key="service.slug"
            :to="'/services/installation'"
            :title="service.title"
            :description="service.shortDesc"
            :icon="service.icon"
            :color="service.color"
            cta="View service"
          />
        </div>
      </div>
    </section>


  </div>
</template>

<script setup lang="ts">
import { services } from '~/data/services'

useSeoMeta({
  title: 'Services — ATT | Installation, Maintenance & Consultancy',
  description: 'ATT provides professional ITS installation, preventive maintenance, expert consultancy, and marine shipping services across Bangladesh.',
})
</script>
