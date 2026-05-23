<template>
  <footer class="bg-primary-900 text-white">
    <!-- Main Footer -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pt-16 pb-10">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-10">

        <!-- Brand Column -->
        <div class="lg:col-span-1">
          <NuxtLink to="/" class="flex items-center gap-3 mb-5">
            <img src="/logo.png" alt="ATT Logo" class="h-12 w-auto" />
          </NuxtLink>
          <p class="text-slate-400 text-sm leading-relaxed mb-6">
            Asian Traffic Technologies Ltd is Bangladesh's leading provider of Intelligent Transportation Systems, toll collection, traffic monitoring, and access control solutions.
          </p>
          <!-- Social -->
          <div class="flex items-center gap-3">
            <a href="#" aria-label="Facebook" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
            </a>
            <a href="#" aria-label="LinkedIn" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            </a>
            <a href="mailto:info@att-bd.com" aria-label="Email" class="social-icon">
              <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"/></svg>
            </a>
          </div>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-white font-semibold text-sm uppercase tracking-wider mb-5 flex items-center gap-2">
            <span class="w-6 h-0.5 bg-accent-500 rounded"></span>
            Quick Links
          </h3>
          <ul class="space-y-2.5">
            <li v-for="link in quickLinks" :key="link.to">
              <NuxtLink :to="link.to" class="footer-link">
                <svg class="w-3.5 h-3.5 text-accent-500 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/>
                </svg>
                {{ link.label }}
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Solutions -->
        <div>
          <h3 class="text-white font-semibold text-sm uppercase tracking-wider mb-5 flex items-center gap-2">
            <span class="w-6 h-0.5 bg-accent-500 rounded"></span>
            Solutions
          </h3>
          <ul class="space-y-2.5">
            <li v-for="s in solutionLinks" :key="s.to">
              <NuxtLink :to="s.to" class="footer-link">
                <svg class="w-3.5 h-3.5 text-accent-500 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5"/>
                </svg>
                {{ s.label }}
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Contact -->
        <div>
          <h3 class="text-white font-semibold text-sm uppercase tracking-wider mb-5 flex items-center gap-2">
            <span class="w-6 h-0.5 bg-accent-500 rounded"></span>
            Contact Us
          </h3>
          <ul class="space-y-4">
            <li class="flex items-start gap-3">
              <div class="w-8 h-8 rounded-lg bg-white/5 flex items-center justify-center flex-shrink-0 mt-0.5">
                <svg class="w-4 h-4 text-accent-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"/><path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"/></svg>
              </div>
              <p class="text-slate-400 text-sm leading-relaxed">House # 67, Road # 27, Flat # 5A, Gulshan Circle-1, Dhaka-1212, Bangladesh</p>
            </li>
            <li class="flex items-center gap-3">
              <div class="w-8 h-8 rounded-lg bg-white/5 flex items-center justify-center flex-shrink-0">
                <svg class="w-4 h-4 text-accent-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z"/></svg>
              </div>
              <div>
                <a href="tel:+88-2-8832313" class="text-slate-400 text-sm hover:text-accent-400 transition-colors block">+88-2-8832313</a>
                <a href="tel:+88-2-8832240" class="text-slate-400 text-sm hover:text-accent-400 transition-colors block">+88-2-8832240</a>
              </div>
            </li>
            <li class="flex items-center gap-3">
              <div class="w-8 h-8 rounded-lg bg-white/5 flex items-center justify-center flex-shrink-0">
                <svg class="w-4 h-4 text-accent-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"/></svg>
              </div>
              <a href="mailto:info@att-bd.com" class="text-slate-400 text-sm hover:text-accent-400 transition-colors">info@att-bd.com</a>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Bottom Bar -->
    <div class="border-t border-white/10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-5 flex flex-col md:flex-row items-center justify-between gap-4 text-sm text-slate-500">
        <p>© {{ currentYear }} Asian Traffic Technologies Ltd. All rights reserved.</p>
        <div class="flex flex-col sm:flex-row items-center gap-4">
          <p>
            Developed by <a href="https://creativetechpark.com/" target="_blank" rel="noopener noreferrer" class="text-accent-500 hover:text-accent-400 transition-colors font-medium">Creative Tech Park</a>
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { solutions } from '~/data/solutions'

const currentYear = new Date().getFullYear()

const quickLinks = [
  { to: '/', label: 'Home' },
  { to: '/about', label: 'About Us' },
  { to: '/solutions', label: 'Solutions' },
  { to: '/products', label: 'Products' },
  { to: '/services', label: 'Services' },
  { to: '/projects', label: 'Projects' },
  { to: '/blogs', label: 'Blogs' },
  { to: '/contact', label: 'Contact Us' },
]

const solutionLinks = solutions.slice(0, 6).map(s => ({
  to: '/solutions/toll-management',
  label: s.title,
}))
</script>

<style scoped>
.footer-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.875rem;
  color: #94a3b8;
  transition: all 0.15s;
}
.footer-link:hover {
  color: #fb923c;
  padding-left: 4px;
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 2rem;
  height: 2rem;
  border-radius: 0.5rem;
  background: rgba(255,255,255,0.05);
  color: #94a3b8;
  transition: all 0.2s;
}
.social-icon:hover {
  background: #f97316;
  color: white;
  transform: translateY(-2px);
}
</style>
