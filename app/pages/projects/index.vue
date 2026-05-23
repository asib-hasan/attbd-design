<template>
  <div>
    <PageHero
      title="Our Projects"
      subtitle="A track record of successful ITS project delivery for government agencies and private sector clients across Bangladesh."
      label="Projects Portfolio"
    />

    <section class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Filter tabs -->
        <div class="flex flex-wrap gap-3 mb-10 justify-center">
          <button
            v-for="cat in categories"
            :key="cat.key"
            :class="[
              'px-5 py-2.5 rounded-xl text-sm font-semibold transition-all duration-200',
              activeCategory === cat.key
                ? 'bg-primary-700 text-white shadow-lg'
                : 'bg-white text-slate-600 border border-slate-200 hover:border-blue-300 hover:text-blue-600',
            ]"
            @click="activeCategory = cat.key"
          >
            {{ cat.label }}
            <span :class="['ml-1.5 text-xs', activeCategory === cat.key ? 'text-white/70' : 'text-slate-400']">
              ({{ cat.key === 'all' ? projects.length : projects.filter(p => p.category === cat.key).length }})
            </span>
          </button>
        </div>

        <!-- Projects grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <NuxtLink
            v-for="project in filteredProjects"
            :key="project.slug"
            :to="`/projects/${project.slug}`"
            class="group bg-white rounded-2xl border border-slate-100 overflow-hidden hover:shadow-xl hover:-translate-y-1 transition-all duration-300"
          >
            <!-- Color bar + icon -->
            <div :class="['h-2 w-full bg-gradient-to-r', project.color]"></div>
            <div class="p-6">
              <div class="flex items-start justify-between mb-4">
                <div :class="['w-12 h-12 rounded-xl bg-gradient-to-br flex items-center justify-center text-white shadow-md', project.color]">
                  <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 21h19.5m-18-18v18m10.5-18v18m6-13.5V21M6.75 6.75h.75m-.75 3h.75m-.75 3h.75m3-6h.75m-.75 3h.75m-.75 3h.75M6.75 21v-3.375c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21M3 3h12m-.75 4.5H21m-3.75 3.75h.008v.008h-.008v-.008zm0 3h.008v.008h-.008v-.008zm0 3h.008v.008h-.008v-.008z"/>
                  </svg>
                </div>
                <span :class="['text-xs font-semibold px-3 py-1 rounded-full', categoryBadge(project.category)]">
                  {{ categoryLabel(project.category) }}
                </span>
              </div>
              <h3 class="font-bold text-slate-900 mb-2 group-hover:text-blue-700 transition-colors leading-snug">{{ project.title }}</h3>
              <p class="text-sm text-slate-500 mb-4 leading-relaxed">{{ project.shortDesc }}</p>
              <div class="flex items-center justify-between text-xs text-slate-400">
                <span>{{ project.client }}</span>
                <span class="font-semibold">{{ project.year }}</span>
              </div>
              <div class="flex items-center gap-1.5 mt-4 text-sm font-semibold text-blue-600 group-hover:gap-3 transition-all duration-200">
                View project
                <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
              </div>
            </div>
          </NuxtLink>
        </div>

        <!-- Empty state -->
        <div v-if="filteredProjects.length === 0" class="text-center py-16 text-slate-400">
          No projects found in this category.
        </div>
      </div>
    </section>


  </div>
</template>

<script setup lang="ts">
import { projects, projectCategories } from '~/data/projects'

useSeoMeta({
  title: 'Projects — ATT | ITS Project Portfolio Bangladesh',
  description: 'Explore ATT\'s portfolio of completed and ongoing ITS projects across Bangladesh — toll systems, traffic monitoring, access control, and more.',
})

const route = useRoute()
const activeCategory = ref((route.query.cat as string) || 'all')

const categories = projectCategories

const filteredProjects = computed(() =>
  activeCategory.value === 'all'
    ? projects
    : projects.filter(p => p.category === activeCategory.value)
)

function categoryLabel(cat: string) {
  return projectCategories.find(c => c.key === cat)?.label ?? cat
}

function categoryBadge(cat: string) {
  const map: Record<string, string> = {
    completed: 'bg-green-50 text-green-700',
    ongoing: 'bg-blue-50 text-blue-700',
    fisheries: 'bg-cyan-50 text-cyan-700',
  }
  return map[cat] ?? 'bg-slate-100 text-slate-600'
}
</script>
