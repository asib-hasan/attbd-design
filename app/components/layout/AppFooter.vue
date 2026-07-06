<template>
  <footer class="relative bg-slate-950 text-slate-400 border-t border-white/5 font-sans pt-20 pb-10">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <!-- Top Section -->
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-10 lg:gap-8 text-sm mb-16">
        
        <!-- Column 1: About Us -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">About Us</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/about" class="footer-link">Company Overview</NuxtLink></li>
            <li><NuxtLink to="/about#mission" class="footer-link">Vision & Mission</NuxtLink></li>
            <li><NuxtLink to="/about#board" class="footer-link">Board of Directors</NuxtLink></li>
            <li><NuxtLink to="/contact" class="footer-link">Careers</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 2: Solutions -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">Solutions</h3>
          <ul class="space-y-4">
            <li v-for="s in solutionLinks" :key="s.to">
              <NuxtLink :to="s.to" class="footer-link">{{ s.label }}</NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Column 3: Products -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">Products</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/products/counters-classifiers" class="footer-link">Traffic Counters</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">Toll Systems</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">Weigh-in-Motion</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">LED Displays</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 4: Quick Links -->
        <div>
          <h3 class="text-white font-bold mb-6 text-base tracking-wide">Quick Links</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/contact" class="footer-link">Contact Us</NuxtLink></li>
            <li><NuxtLink to="/blogs" class="footer-link">News & Events</NuxtLink></li>
            <li><NuxtLink to="/projects" class="footer-link">Our Projects</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 5: Brand & Social -->
        <div class="col-span-2 lg:col-span-1">
          <NuxtLink to="/" class="inline-block mb-6">
            <img src="/logo.png" alt="ATT Logo" class="h-14 lg:h-16 w-auto opacity-90 hover:opacity-100 transition-opacity" />
          </NuxtLink>
          <p class="text-xs leading-relaxed mb-6">
            Asian Traffic Technologies Ltd. Providing end-to-end infrastructure solutions for a modern Bangladesh.
          </p>
          <div class="flex items-center gap-3">
            <a href="mailto:info@att-bd.com" aria-label="Email" class="social-icon">
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                <polyline points="22,6 12,13 2,6"></polyline>
              </svg>
            </a>
          </div>
        </div>
      </div>
      
      <!-- Bottom Bar -->
      <div class="border-t border-white/5 pt-8 flex flex-col md:flex-row items-center justify-between gap-4 text-xs text-slate-500">
        <p>© {{ currentYear }} Asian Traffic Technologies Ltd. All Rights Reserved.</p>
        <p>
          Developed By <a href="https://creativetechpark.com/" target="_blank" rel="noopener noreferrer" class="text-slate-300 hover:text-white font-medium transition-colors">Creative Tech Park</a>
        </p>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { solutions } from '~/data/solutions'

const currentYear = new Date().getFullYear()

const solutionLinks = solutions.slice(0, 4).map(s => ({
  to: `/solutions#${s.slug}`,
  label: s.title,
}))
</script>

<style scoped>
.footer-link {
  display: inline-block;
  font-size: 0.875rem;
  color: #94a3b8; /* slate-400 */
  transition: all 0.2s ease;
}
.footer-link:hover {
  color: #ffffff;
  transform: translateX(2px);
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 2.25rem;
  height: 2.25rem;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.05);
  color: #94a3b8;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.2s ease;
}
.social-icon:hover {
  background: rgba(255, 255, 255, 0.1);
  color: #ffffff;
  border-color: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}
</style>
