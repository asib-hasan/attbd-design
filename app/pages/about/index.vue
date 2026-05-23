<template>
  <div>
    <PageHero
      title="About Asian Traffic Technologies"
      subtitle="Bangladesh's leading Intelligent Transportation Systems provider — over 25 years of excellence in toll collection, traffic monitoring, and infrastructure technology."
      label="Company Overview"
    />

    <!-- Company Intro -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-2 gap-16 items-center">
          <div>
            <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-blue-50 text-blue-700 text-xs font-semibold rounded-full border border-blue-100 mb-5">
              Who We Are
            </div>
            <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-6 leading-tight">
              Asian Traffic Technologies Ltd (ATT)
            </h2>
            <p class="text-slate-500 leading-relaxed mb-5">
              ATT is a multi-dimensional business-oriented company having activities in the sectors of Toll Management & Operation, Ship Building, Navigation & Ship Rescue, Weighing Management, Civil Work & Building Construction, Human & Vehicle Access Control Systems, CCTV Surveillance & Security Systems, and Parking Management.
            </p>
            <p class="text-slate-500 leading-relaxed">
              With a multidisciplinary team of engineers, technicians, and project managers, we bring together expertise in electronics, software, civil engineering, and project management to deliver complete solutions that perform reliably in Bangladesh's demanding environment.
            </p>
          </div>

          <!-- Stats -->
          <div class="grid grid-cols-2 gap-5">
            <div v-for="s in companyStats" :key="s.label" :class="['rounded-2xl p-8 text-center', s.bg]">
              <div :class="['text-4xl font-black mb-2', s.color]">{{ s.value }}</div>
              <div class="text-sm font-semibold text-slate-700">{{ s.label }}</div>
              <div class="text-xs text-slate-400 mt-1">{{ s.sub }}</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Mission & Vision -->
    <section id="mission" class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-14">
          <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-blue-50 text-blue-700 text-xs font-semibold rounded-full border border-blue-100 mb-4">
            Our Direction
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">Mission & Vision</h2>
          <p class="text-slate-500 max-w-xl mx-auto">The guiding principles that define our strategy and drive our commitment to excellence.</p>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
          <div id="mission" class="bg-white rounded-2xl border border-slate-100 p-8 shadow-sm hover:shadow-lg transition-shadow">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-blue-500 to-blue-700 flex items-center justify-center text-white mb-6">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M15.59 14.37a6 6 0 01-5.84 7.38v-4.8m5.84-2.58a14.98 14.98 0 006.16-12.12A14.98 14.98 0 009.631 8.41m5.96 5.96a14.926 14.926 0 01-5.841 2.58m-.119-8.54a6 6 0 00-7.381 5.84h4.8m2.581-5.84a14.927 14.927 0 00-2.58 5.84m2.699 2.7c-.103.021-.207.041-.311.06a15.09 15.09 0 01-2.448-2.448 14.9 14.9 0 01.06-.312m-2.24 2.39a4.493 4.493 0 00-1.757 4.306 4.493 4.493 0 004.306-1.758M16.5 9a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0z"/></svg>
            </div>
            <h3 class="text-xl font-bold text-slate-900 mb-3">Our Missions</h3>
            <ul class="text-slate-500 leading-relaxed list-disc list-inside ml-2 space-y-3">
              <li>To hold the leadership in Bangladesh by means of continuous strive in offering quality management for Operation & Maintenance of ETC for Roads & Highways.</li>
              <li>To become the market leader for Highways Systems Technology development in Bangladesh.</li>
              <li>To provide proper security system all over Bangladesh.</li>
            </ul>
          </div>

          <div id="vision" class="bg-white rounded-2xl border border-slate-100 p-8 shadow-sm hover:shadow-lg transition-shadow">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-accent-500 to-orange-600 flex items-center justify-center text-white mb-6">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M2.036 12.322a1.012 1.012 0 010-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178z"/><path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
            </div>
            <h3 class="text-xl font-bold text-slate-900 mb-3">Our Vision</h3>
            <p class="text-slate-500 leading-relaxed mb-4">
              In a world where complexity increasingly touches every aspect of our daily lives, we will lead in bringing sense and simplicity to people.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- A Glimpse of ATT -->
    <section id="glimpse" class="py-24 bg-white relative overflow-hidden border-t border-slate-100">
      <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center">
        <div class="inline-flex items-center gap-2 px-4 py-2 bg-blue-50 text-blue-700 text-sm font-semibold rounded-full border border-blue-100 mb-10 shadow-sm">
          A Glimpse of ATT
        </div>
        
        <div class="space-y-8 text-lg md:text-xl text-slate-600 leading-relaxed font-light">
          <p>
            It is the sincere efforts and aggressive leadership having dynamic visions of <span class="text-slate-900 font-medium">Engineer Mehboob Kabir</span> without whose dedicated persuasion, ATT would not have reached on its present stand now.
          </p>
          <p>
            Since the Inception of ATT in the year 2002, ATT now could now play as a market leader of ETC (Electronic Toll Collection Systems, Operation and Maintenance) for Roads & Highways of Bangladesh, Human & Vehicle Access System as well as security system, Ship Building and Operation. About 80% of total market share of above business is now being enjoyed by ATT and its Associates.
          </p>
          <p>
            The company though made its further strive putting its footage into other business arena whilst ETC remains the core business of the company.
          </p>
        </div>
      </div>
    </section>

    <!-- Sister Concerns -->
    <section class="py-20 bg-white border-t border-slate-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-14">
          <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-green-50 text-green-700 text-xs font-semibold rounded-full border border-green-100 mb-4">
            Our Group
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">Sister Concerns</h2>
          <p class="text-slate-500 max-w-xl mx-auto">Asian Traffic Technologies is part of a larger multidimensional business group operating across diverse sectors in Bangladesh.</p>
        </div>

        <div class="grid md:grid-cols-4 gap-6">
          <div class="bg-slate-50 rounded-2xl p-6 border border-slate-100 text-center hover:shadow-md transition-shadow">
            <div class="w-12 h-12 bg-white rounded-xl shadow-sm flex items-center justify-center mx-auto mb-4 text-blue-600">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
            </div>
            <h3 class="font-bold text-slate-900 mb-2">Mehboob & Masood Navigation</h3>
            <p class="text-xs text-slate-500">Ship Operation & Logistics</p>
          </div>
          <div class="bg-slate-50 rounded-2xl p-6 border border-slate-100 text-center hover:shadow-md transition-shadow">
            <div class="w-12 h-12 bg-white rounded-xl shadow-sm flex items-center justify-center mx-auto mb-4 text-cyan-600">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>
            </div>
            <h3 class="font-bold text-slate-900 mb-2">Shams Navigation</h3>
            <p class="text-xs text-slate-500">Carrier Operation</p>
          </div>
          <div class="bg-slate-50 rounded-2xl p-6 border border-slate-100 text-center hover:shadow-md transition-shadow">
            <div class="w-12 h-12 bg-white rounded-xl shadow-sm flex items-center justify-center mx-auto mb-4 text-indigo-600">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" /></svg>
            </div>
            <h3 class="font-bold text-slate-900 mb-2">Engineer Mehboob Ship Builders</h3>
            <p class="text-xs text-slate-500">Ship Building & Manufacturing</p>
          </div>
          <div class="bg-slate-50 rounded-2xl p-6 border border-slate-100 text-center hover:shadow-md transition-shadow">
            <div class="w-12 h-12 bg-white rounded-xl shadow-sm flex items-center justify-center mx-auto mb-4 text-emerald-600">
              <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" /></svg>
            </div>
            <h3 class="font-bold text-slate-900 mb-2">A M Corporation</h3>
            <p class="text-xs text-slate-500">General Trading & Supply</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Board of Directors -->
    <section id="board" class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-14">
          <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-blue-50 text-blue-700 text-xs font-semibold rounded-full border border-blue-100 mb-4">
            Leadership
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">Board of Directors</h2>
          <p class="text-slate-500 max-w-xl mx-auto">Experienced leadership driving ATT's vision for Bangladesh's transportation future.</p>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <div v-for="member in board" :key="member.name" class="bg-white rounded-2xl border border-slate-100 p-8 text-center shadow-sm hover:shadow-lg transition-all duration-300 hover:-translate-y-1">
            <div class="w-28 h-28 rounded-full mx-auto mb-5 overflow-hidden border-4 border-slate-50 shadow-md">
              <img :src="`/People_images/${member.image}`" :alt="member.name" class="w-full h-full object-cover object-top" />
            </div>
            <h3 class="text-lg font-bold text-slate-900 mb-1">{{ member.name }}</h3>
            <div class="text-sm font-semibold text-blue-600 mb-3">{{ member.title }}</div>
            <p class="text-xs text-slate-400 leading-relaxed">{{ member.bio }}</p>
          </div>
        </div>
      </div>
    </section>


  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'About ATT — Asian Traffic Technologies Ltd',
  description: 'Learn about Asian Traffic Technologies Ltd — our mission, vision, board of directors, and 25+ years of delivering ITS solutions in Bangladesh.',
})

const companyStats = [
  { value: '2002', label: 'Year Established', sub: 'Inception of ATT', bg: 'bg-blue-50', color: 'text-blue-700' },
  { value: '80%', label: 'Market Share', sub: 'In Core Businesses', bg: 'bg-accent-50', color: 'text-accent-600' },
  { value: '500+', label: 'Workforce', sub: 'Technical & Commercial', bg: 'bg-green-50', color: 'text-green-700' },
  { value: '31', label: 'Owned Vessels', sub: 'Cargo & Tankers', bg: 'bg-purple-50', color: 'text-purple-700' },
]



const board = [
  {
    name: 'Engr. Mehboob Kabir',
    image: 'mehboob_kabir.PNG',
    title: 'Managing Director & Founder',
    bio: 'B.Sc in CSE, DBA from Mehran Engineering University, Pakistan. Since 1998, he has guided ATT\'s business strategies, strategic alliances, and rapid growth.',
  },
  {
    name: 'Dr. Sifat Farhana Nahid',
    image: 'sifat_farhana.PNG',
    title: 'Deputy Managing Director (DMD)',
    bio: 'M.B.B.S in Dhaka National Medical College. Key person in Public Relation and Finance Division, ensuring the company\'s operational and financial health.',
  },
  {
    name: 'Md. Masood Karim',
    image: 'masood_karim.PNG',
    title: 'Chief Executive Officer (CEO)',
    bio: 'M.B.A from University of Technology, Sydney. With ATT since 2002, managing teams of professionals involved in local and international markets.',
  },
  {
    name: 'Md. Shafat Kader Siddiky',
    image: 'shafat.PNG',
    title: 'Director — Business Development',
    bio: 'MBA from UK. Joined ATT in 2006, managing the company\'s overall business development issues across various departments locally and internationally.',
  },
]
</script>
