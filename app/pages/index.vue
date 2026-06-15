<template>
  <div>
    <HeroSection />
    <MissionSection />
    
    <AlternatingGrid 
      title="Core Sectors" 
      highlight="Our" 
      description="We provide comprehensive solutions across multiple infrastructure sectors."
      :items="sectors" 
    />

    <StatsSection />

    <TestimonialsSection />

    <BlogSection />
    <ClientsSection />

  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

useSeoMeta({
  title: 'ATT — Asian Traffic Technologies Ltd | Infrastructure Solutions',
  description: 'Asian Traffic Technologies Ltd — Bangladesh\'s leading provider of Electronic Toll Management, Weighing Systems, Civil Works, and Shipbuilding.',
})

const sectors = ref([
  {
    title: 'Electronic Toll Management & Operation',
    description: 'We supply, install, manage, and operate Electronic Toll Collection (ETC) systems and web-based online weighing toll systems across major bridges and highways.',
    image: '/slider/hero_toll_collection.png',
    features: ['ETC Equipment Supply & Installation', 'Management and Operation', 'Web-based Online Weighing Toll System'],
    link: '/solutions/toll-management'
  },
  {
    title: 'Civil Work & Building Construction',
    description: 'As contractors and builders, we execute major government projects for LGED, RHD, CPA, BLPA, BBA, and RAJUK.',
    image: '/slider/hero_traffic_system.png',
    features: ['Civil Contractors & Builders', 'Government Infrastructure Projects', 'Bridge & Road Construction'],
    link: '/services#civil-construction'
  },
  {
    title: 'Ship Building & Navigation',
    description: 'Through our sister concerns, we manage ship building, operations, and navigation solutions.',
    image: '/slider/hero_access_security.png', // We can replace this image later
    features: ['Ship Building', 'Carrier Operation', 'Navigation Management'],
    link: '/services#shams-navigation'
  },
  {
    title: 'Weighing Management (WIM)',
    description: 'Weigh in Motion (WIM) systems and Weighing Scale Stations (Weighbridge) including integrated software solutions.',
    image: '/slider/hero_traffic_system.png', // Placeholders
    features: ['High Speed WIM Systems', 'Weighbridge Installation', 'Software Integration'],
    link: '/products/weigh-in-motion'
  },
])
</script>
