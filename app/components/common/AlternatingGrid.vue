<template>
  <div class="py-24 bg-slate-950">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <!-- Section Header -->
      <div v-if="title || description" class="text-center mb-24">
        <h2 v-animate="'animate-fade-up'" class="text-4xl md:text-5xl font-black text-white uppercase tracking-tight mb-6">
          <span v-if="highlight" class="text-accent-500 mr-2">{{ highlight }}</span>{{ title }}
        </h2>
        <p v-if="description" v-animate="'animate-fade-up delay-100'" class="text-lg text-slate-400 max-w-3xl mx-auto leading-relaxed">
          {{ description }}
        </p>
      </div>

      <!-- Grid Items -->
      <div class="space-y-24 md:space-y-32">
        <div 
          v-for="(item, index) in items" 
          :key="index"
          :id="item.id"
          class="flex flex-col md:flex-row gap-12 lg:gap-20 items-center scroll-mt-32"
          :class="{'md:flex-row-reverse': index % 2 !== 0}"
        >
          <!-- Image Container -->
          <div v-animate="index % 2 !== 0 ? 'animate-slide-left' : 'animate-fade-up'" class="w-full md:w-1/2 relative group overflow-hidden border border-white/10 shadow-2xl rounded-3xl">
            <!-- Dark Overlay that fades on hover -->
            <div class="absolute inset-0 bg-slate-950/40 group-hover:bg-slate-950/10 transition-colors duration-700 z-10"></div>
            <img 
              :src="item.image" 
              :alt="item.title"
              class="w-full h-[350px] md:h-[450px] object-cover transition-transform duration-1000 group-hover:scale-110"
            />
            <!-- Accent Corner -->
            <div class="absolute bottom-0 right-0 w-16 h-16 bg-white/10 backdrop-blur-md border-t border-l border-white/20 z-20 flex items-center justify-center text-accent-500 group-hover:bg-accent-500 group-hover:text-slate-900 transition-all duration-300 rounded-tl-3xl">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5v15m7.5-7.5h-15" />
              </svg>
            </div>
          </div>

          <!-- Content Container -->
          <div v-animate="index % 2 === 0 ? 'animate-slide-left' : 'animate-fade-up'" class="w-full md:w-1/2 flex flex-col justify-center">
            <div class="border-l-[4px] border-accent-500 pl-6 mb-8">
              <h3 class="text-3xl md:text-4xl font-black text-white uppercase tracking-tight mb-6">
                {{ item.title }}
              </h3>
              <p class="text-slate-400 text-lg leading-relaxed">
                {{ item.description }}
              </p>
            </div>
            
            <ul v-if="item.features" class="space-y-4 mb-10">
              <li v-for="(feature, fIndex) in item.features" :key="fIndex" class="flex items-start gap-4">
                <div class="mt-1 w-6 h-6 rounded-full bg-white/5 border border-white/10 flex items-center justify-center flex-shrink-0">
                  <svg class="w-3.5 h-3.5 text-accent-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="3">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 12.75l6 6 9-13.5" />
                  </svg>
                </div>
                <span class="text-slate-300 text-base">{{ feature }}</span>
              </li>
            </ul>

            <div>
              <NuxtLink 
                v-if="item.link" 
                :to="item.link"
                class="inline-flex items-center justify-center gap-3 px-8 py-4 bg-white/5 border border-white/10 hover:border-white/20 hover:bg-white/10 text-white font-bold uppercase tracking-wider rounded-full transition-all duration-300 group/btn"
              >
                {{ item.linkLabel || 'Learn More' }}
                <svg class="w-5 h-5 text-accent-500 group-hover/btn:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
                </svg>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup lang="ts">
export interface GridItem {
  id?: string
  title: string
  description: string
  image: string
  features?: string[]
  link?: string
  linkLabel?: string
}

defineProps<{
  title?: string
  highlight?: string
  description?: string
  items: GridItem[]
}>()
</script>
