<template>
  <!-- Top Info Bar -->
  <div class="hidden md:block bg-primary-900 text-white/70 text-xs py-2">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex items-center justify-between">
      <div class="flex items-center gap-6">
        <a href="tel:+88-2-8832313" class="flex items-center gap-1.5 hover:text-accent-400 transition-colors">
          <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z"/>
          </svg>
          +88-2-8832313
        </a>
        <a href="mailto:info@att-bd.com" class="flex items-center gap-1.5 hover:text-accent-400 transition-colors">
          <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"/>
          </svg>
          info@att-bd.com
        </a>
      </div>
      <div class="flex items-center gap-1.5">
        <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"/>
          <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"/>
        </svg>
        House #67, Road #27, Gulshan Circle #1, Dhaka-1212
      </div>
    </div>
  </div>

  <!-- Main Navigation -->
  <header class="sticky top-0 z-50 bg-white/95 backdrop-blur-md shadow-lg border-b border-slate-200/80">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 lg:h-20">

        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center gap-3 flex-shrink-0">
          <img src="/logo.jpeg" alt="ATT Logo" class="h-10 lg:h-12 w-auto mix-blend-multiply" />
          <div class="hidden sm:block">
            <div class="font-bold text-base leading-tight text-primary-700">
              Asian Traffic Technologies
            </div>
            <div class="text-xs text-slate-500">
              Ltd. — Dhaka, Bangladesh
            </div>
          </div>
        </NuxtLink>

        <!-- Desktop Nav -->
        <nav class="hidden lg:flex items-center gap-1">
          <NuxtLink
            to="/"
            :class="navLinkClass"
            active-class="!text-accent-500"
          >Home</NuxtLink>

          <!-- About Us dropdown -->
          <div class="relative" @mouseenter="openDropdown('about')" @mouseleave="closeDropdown">
            <NuxtLink
              to="/about"
              :class="[navLinkClass, 'flex items-center gap-1']"
              active-class="!text-accent-500"
            >
              About Us
              <svg class="w-3.5 h-3.5 transition-transform duration-200" :class="{ 'rotate-180': activeDropdown === 'about' }" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5"/>
              </svg>
            </NuxtLink>
            <Transition name="dropdown">
              <div v-if="activeDropdown === 'about'" class="absolute top-full left-0 mt-1 w-52 bg-white rounded-xl shadow-xl border border-slate-100 overflow-hidden py-2">
                <NuxtLink v-for="item in aboutLinks" :key="item.to" :to="item.to" class="dropdown-item" @click="closeDropdown">{{ item.label }}</NuxtLink>
              </div>
            </Transition>
          </div>

          <!-- Solutions dropdown -->
          <div class="relative" @mouseenter="openDropdown('solutions')" @mouseleave="closeDropdown">
            <NuxtLink to="/solutions" :class="[navLinkClass, 'flex items-center gap-1']" active-class="!text-accent-500">
              Solutions
              <svg class="w-3.5 h-3.5 transition-transform duration-200" :class="{ 'rotate-180': activeDropdown === 'solutions' }" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5"/>
              </svg>
            </NuxtLink>
            <Transition name="dropdown">
              <div v-if="activeDropdown === 'solutions'" class="absolute top-full left-0 mt-1 w-72 bg-white rounded-xl shadow-xl border border-slate-100 overflow-hidden py-2">
                <NuxtLink v-for="s in solutionsLinks" :key="s.to" :to="s.to" class="dropdown-item" @click="closeDropdown">{{ s.label }}</NuxtLink>
              </div>
            </Transition>
          </div>

          <!-- Products dropdown -->
          <div class="relative" @mouseenter="openDropdown('products')" @mouseleave="closeDropdown">
            <NuxtLink to="/products" :class="[navLinkClass, 'flex items-center gap-1']" active-class="!text-accent-500">
              Products
              <svg class="w-3.5 h-3.5 transition-transform duration-200" :class="{ 'rotate-180': activeDropdown === 'products' }" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5"/>
              </svg>
            </NuxtLink>
            <Transition name="dropdown">
              <div v-if="activeDropdown === 'products'" class="absolute top-full left-0 mt-1 w-72 bg-white rounded-xl shadow-xl border border-slate-100 overflow-hidden py-2">
                <NuxtLink v-for="p in productsLinks" :key="p.to" :to="p.to" class="dropdown-item" @click="closeDropdown">{{ p.label }}</NuxtLink>
              </div>
            </Transition>
          </div>

          <!-- Services dropdown -->
          <div class="relative" @mouseenter="openDropdown('services')" @mouseleave="closeDropdown">
            <NuxtLink to="/services" :class="[navLinkClass, 'flex items-center gap-1']" active-class="!text-accent-500">
              Services
              <svg class="w-3.5 h-3.5 transition-transform duration-200" :class="{ 'rotate-180': activeDropdown === 'services' }" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5"/>
              </svg>
            </NuxtLink>
            <Transition name="dropdown">
              <div v-if="activeDropdown === 'services'" class="absolute top-full left-0 mt-1 w-64 bg-white rounded-xl shadow-xl border border-slate-100 overflow-hidden py-2">
                <NuxtLink v-for="s in servicesLinks" :key="s.to" :to="s.to" class="dropdown-item" @click="closeDropdown">{{ s.label }}</NuxtLink>
              </div>
            </Transition>
          </div>

          <!-- Projects dropdown -->
          <div class="relative" @mouseenter="openDropdown('projects')" @mouseleave="closeDropdown">
            <NuxtLink to="/projects" :class="[navLinkClass, 'flex items-center gap-1']" active-class="!text-accent-500">
              Projects
              <svg class="w-3.5 h-3.5 transition-transform duration-200" :class="{ 'rotate-180': activeDropdown === 'projects' }" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5"/>
              </svg>
            </NuxtLink>
            <Transition name="dropdown">
              <div v-if="activeDropdown === 'projects'" class="absolute top-full left-0 mt-1 w-56 bg-white rounded-xl shadow-xl border border-slate-100 overflow-hidden py-2">
                <NuxtLink v-for="p in projectsLinks" :key="p.to" :to="p.to" class="dropdown-item" @click="closeDropdown">{{ p.label }}</NuxtLink>
              </div>
            </Transition>
          </div>

          <NuxtLink
            to="/blogs"
            :class="navLinkClass"
            active-class="!text-accent-500"
          >Blogs</NuxtLink>

          <NuxtLink to="/contact" class="ml-2 px-5 py-2.5 bg-accent-500 hover:bg-accent-600 text-white text-sm font-semibold rounded-lg transition-all duration-200 hover:scale-105 shadow-lg shadow-orange-500/20">
            Contact Us
          </NuxtLink>
        </nav>

        <button
          class="lg:hidden p-2 rounded-lg transition-colors text-slate-700 hover:bg-slate-100"
          @click="mobileOpen = !mobileOpen"
          aria-label="Toggle menu"
        >
          <svg v-if="!mobileOpen" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"/>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition name="dropdown">
      <div v-if="mobileOpen" class="lg:hidden bg-white border-t border-slate-200 shadow-xl">
        <div class="max-w-7xl mx-auto px-4 py-4 space-y-1">
          <NuxtLink to="/" class="mobile-nav-link" @click="mobileOpen = false">Home</NuxtLink>
          <NuxtLink to="/about" class="mobile-nav-link" @click="mobileOpen = false">About Us</NuxtLink>
          <NuxtLink to="/solutions" class="mobile-nav-link" @click="mobileOpen = false">Solutions</NuxtLink>
          <NuxtLink to="/products" class="mobile-nav-link" @click="mobileOpen = false">Products</NuxtLink>
          <NuxtLink to="/services" class="mobile-nav-link" @click="mobileOpen = false">Services</NuxtLink>
          <NuxtLink to="/projects" class="mobile-nav-link" @click="mobileOpen = false">Projects</NuxtLink>
          <NuxtLink to="/blogs" class="mobile-nav-link" @click="mobileOpen = false">Blogs</NuxtLink>
          <NuxtLink to="/contact" class="block mt-3 px-4 py-3 bg-accent-500 text-white text-sm font-semibold rounded-lg text-center" @click="mobileOpen = false">Contact Us</NuxtLink>
        </div>
      </div>
    </Transition>
  </header>
</template>

<script setup lang="ts">
import { solutions } from '~/data/solutions'
import { products } from '~/data/products'
import { services } from '~/data/services'

const activeDropdown = ref<string | null>(null)
const mobileOpen = ref(false)

let closeTimer: ReturnType<typeof setTimeout> | null = null

function openDropdown(name: string) {
  if (closeTimer) clearTimeout(closeTimer)
  activeDropdown.value = name
}

function closeDropdown() {
  closeTimer = setTimeout(() => {
    activeDropdown.value = null
  }, 150)
}

const navLinkClass = 'nav-link-dark px-3 py-2 rounded-md'

const aboutLinks = [
  { to: '/about', label: 'Company Overview' },
  { to: '/about#board', label: 'Board of Directors' },
  { to: '/about#mission', label: 'Our Mission' },
  { to: '/about#vision', label: 'Our Vision' },
  { to: '/about#glimpse', label: 'A Glimpse of ATT' },
]

const solutionsLinks = solutions.map(s => ({ to: `/solutions/${s.slug}`, label: s.title }))
const productsLinks = products.map(p => ({ to: `/products/${p.slug}`, label: p.title }))
const servicesLinks = services.map(s => ({ to: `/services/${s.slug}`, label: s.title }))

const projectsLinks = [
  { to: '/projects?cat=completed', label: 'Completed Projects' },
  { to: '/projects?cat=ongoing', label: 'On Going Projects' },
  { to: '/projects?cat=fisheries', label: 'Fisheries' },
]
</script>

<style scoped>
.dropdown-item {
  display: block;
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
  color: #374151;
  transition: all 0.15s;
}
.dropdown-item:hover {
  background: #eff6ff;
  color: #2563eb;
  padding-left: 1.25rem;
}

.mobile-nav-link {
  display: block;
  padding: 0.75rem 1rem;
  font-size: 0.9rem;
  font-weight: 500;
  color: #1e293b;
  border-radius: 0.5rem;
  transition: all 0.15s;
}
.mobile-nav-link:hover {
  background: #eff6ff;
  color: #2563eb;
}
</style>
