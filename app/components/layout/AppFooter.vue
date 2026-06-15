<template>
  <footer class="relative bg-[#0054A6] text-white overflow-hidden font-sans">
    <!-- Wavy Background -->
    <div class="absolute inset-0 pointer-events-none opacity-20 z-0">
      <svg class="w-full h-full" preserveAspectRatio="none" viewBox="0 0 1440 320" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M0 160C120 160 240 220 360 220C480 220 600 160 720 160C840 160 960 220 1080 220C1200 220 1320 160 1440 160V320H0V160Z" fill="#ffffff" />
        <path fill-rule="evenodd" clip-rule="evenodd" d="M0 240C120 240 240 180 360 180C480 180 600 240 720 240C840 240 960 180 1080 180C1200 180 1320 240 1440 240V320H0V240Z" fill="#ffffff" opacity="0.5" />
      </svg>
    </div>

    <!-- Main Footer Content -->
    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pt-16 pb-12">
      <!-- Top Horizontal Dotted Line -->
      <div class="w-full border-t border-dashed border-white/30 mb-8"></div>

      <!-- 5 Column Grid -->
      <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-y-10 text-sm">
        
        <!-- Column 1: About Us -->
        <div class="lg:border-r lg:border-dashed lg:border-white/30 pr-4">
          <h3 class="text-white font-bold mb-6">About Us</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/about" class="footer-link">As unique as you</NuxtLink></li>
            <li><NuxtLink to="/about#mission" class="footer-link">Vision & Mission</NuxtLink></li>
            <li><NuxtLink to="/about" class="footer-link">Heritage</NuxtLink></li>
            <li><NuxtLink to="/about" class="footer-link">Values & Principles</NuxtLink></li>
            <li><NuxtLink to="/about#board" class="footer-link">Our People</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 2: Solutions -->
        <div class="lg:border-r lg:border-dashed lg:border-white/30 px-4">
          <h3 class="text-white font-bold mb-6">Solutions</h3>
          <ul class="space-y-4">
            <li v-for="s in solutionLinks" :key="s.to">
              <NuxtLink :to="s.to" class="footer-link">{{ s.label }}</NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Column 3: Products -->
        <div class="lg:border-r lg:border-dashed lg:border-white/30 px-4">
          <h3 class="text-white font-bold mb-6">Products</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/products/counters-classifiers" class="footer-link">Traffic Counters</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">Toll Systems</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">Weigh-in-Motion</NuxtLink></li>
            <li><NuxtLink to="/products" class="footer-link">LED Displays</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 4: Short Links -->
        <div class="lg:border-r lg:border-dashed lg:border-white/30 px-4">
          <h3 class="text-white font-bold mb-6">Short Links</h3>
          <ul class="space-y-4">
            <li><NuxtLink to="/career" class="footer-link">Career</NuxtLink></li>
            <li><NuxtLink to="/contact" class="footer-link">Contact Us</NuxtLink></li>
            <li><NuxtLink to="/blogs" class="footer-link">News & Events</NuxtLink></li>
            <li><NuxtLink to="/about" class="footer-link">Testimonials</NuxtLink></li>
            <li><NuxtLink to="/projects" class="footer-link">Media Content</NuxtLink></li>
          </ul>
        </div>

        <!-- Column 5: Social Link -->
        <div class="pl-4">
          <h3 class="text-white font-bold mb-6">Social Link</h3>
          <div class="mb-4 text-white/90">Follow us</div>
          <div class="flex items-center gap-2">
            <a href="#" aria-label="Facebook" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
            </a>
            <a href="#" aria-label="Instagram" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
            </a>
            <a href="#" aria-label="Twitter" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
            </a>
            <a href="#" aria-label="YouTube" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.5 12 3.5 12 3.5s-7.505 0-9.377.55a3.016 3.016 0 0 0-2.122 2.136C0 8.07 0 12 0 12s0 3.93.501 5.814a3.016 3.016 0 0 0 2.122 2.136c1.872.55 9.377.55 9.377.55s7.505 0 9.377-.55a3.016 3.016 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
            </a>
            <a href="#" aria-label="LinkedIn" class="social-icon">
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            </a>
          </div>
        </div>

      </div>
      
      <!-- Bottom Horizontal Dotted Line -->
      <div class="w-full border-t border-dashed border-white/30 mt-8"></div>
    </div>

    <!-- Bottom Bar -->
    <div class="relative z-10 border-t border-white/10 mt-2">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6 flex flex-col md:flex-row items-center justify-between gap-4 text-sm text-white/90">
        
        <!-- Logo Left -->
        <NuxtLink to="/" class="flex items-center gap-3">
          <img src="/logo.png" alt="ATT Logo" class="h-8 w-auto brightness-0 invert" />
          <div class="font-black text-lg italic text-white uppercase tracking-widest leading-none">
            Asian Traffic Technologies Limited
          </div>
        </NuxtLink>

        <!-- Copyright Right -->
        <div class="flex flex-col md:items-end gap-1">
          <p>© {{ currentYear }}, All Rights Reserved</p>
          <p class="text-white/70 text-xs mt-1">Developed By <a href="https://creativetechpark.com/" target="_blank" rel="noopener noreferrer" class="text-white font-medium hover:underline cursor-pointer">Creative Tech Park</a></p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { solutions } from '~/data/solutions'

const currentYear = new Date().getFullYear()

const solutionLinks = solutions.slice(0, 5).map(s => ({
  to: `/solutions#${s.slug}`,
  label: s.title,
}))
</script>

<style scoped>
.footer-link {
  display: block;
  font-size: 0.875rem;
  color: rgba(255, 255, 255, 0.85);
  transition: all 0.2s;
}
.footer-link:hover {
  color: #ffffff;
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 2.25rem;
  height: 2.25rem;
  border-radius: 50%;
  background: #ffffff;
  color: #0054A6;
  transition: all 0.2s;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}
.social-icon:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 8px rgba(0,0,0,0.15);
}
</style>
