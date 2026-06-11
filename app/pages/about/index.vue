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
          <div id="mission" class="bg-white border border-slate-200 border-l-4 border-l-primary-600 p-8 shadow-sm hover:shadow-md transition-shadow">
            <h3 class="text-xl font-black text-slate-900 uppercase tracking-wide mb-4">Our Missions</h3>
            <ul class="text-slate-600 leading-relaxed list-disc list-inside ml-2 space-y-3">
              <li>To hold the leadership in Bangladesh by means of continuous strive in offering quality management for Operation & Maintenance of ETC for Roads & Highways.</li>
              <li>To become the market leader for Highways Systems Technology development in Bangladesh.</li>
              <li>To provide proper security system all over Bangladesh.</li>
            </ul>
          </div>

          <div id="vision" class="bg-white border border-slate-200 border-l-4 border-l-accent-500 p-8 shadow-sm hover:shadow-md transition-shadow">
            <h3 class="text-xl font-black text-slate-900 uppercase tracking-wide mb-4">Our Vision</h3>
            <p class="text-slate-600 leading-relaxed">
              In a world where complexity increasingly touches every aspect of our daily lives, we will lead in bringing sense and simplicity to people.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Company History -->
    <section id="glimpse" class="py-24 bg-white relative overflow-hidden border-t border-slate-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
        <div class="text-center mb-10">
          <div class="inline-flex items-center gap-2 px-4 py-2 bg-blue-50 text-blue-700 text-sm font-semibold rounded-full border border-blue-100 mb-4 shadow-sm">
            Company History
          </div>
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">A Glimpse of ATT</h2>
        </div>
        
        <Timeline :events="historyEvents" />
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
          <div class="bg-slate-50 border-t-2 border-slate-200 p-6 text-center hover:border-blue-600 transition-colors">
            <h3 class="font-bold text-slate-900 uppercase text-sm tracking-wide mb-2 mt-2">Mehboob & Masood Navigation</h3>
            <p class="text-sm text-slate-500">Ship Operation & Logistics</p>
          </div>
          <div class="bg-slate-50 border-t-2 border-slate-200 p-6 text-center hover:border-cyan-600 transition-colors">
            <h3 class="font-bold text-slate-900 uppercase text-sm tracking-wide mb-2 mt-2">Shams Navigation</h3>
            <p class="text-sm text-slate-500">Carrier Operation</p>
          </div>
          <div class="bg-slate-50 border-t-2 border-slate-200 p-6 text-center hover:border-indigo-600 transition-colors">
            <h3 class="font-bold text-slate-900 uppercase text-sm tracking-wide mb-2 mt-2">Engineer Mehboob Ship Builders</h3>
            <p class="text-sm text-slate-500">Ship Building & Manufacturing</p>
          </div>
          <div class="bg-slate-50 border-t-2 border-slate-200 p-6 text-center hover:border-emerald-600 transition-colors">
            <h3 class="font-bold text-slate-900 uppercase text-sm tracking-wide mb-2 mt-2">A M Corporation</h3>
            <p class="text-sm text-slate-500">General Trading & Supply</p>
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

const historyEvents = [
  {
    year: '2002',
    title: 'Company Inception',
    description: 'ATT was founded by Engineer Mehboob Kabir with a vision to revolutionize toll management in Bangladesh.'
  },
  {
    year: '2010',
    title: 'Market Leadership in ETC',
    description: 'Achieved a dominant market position, handling Electronic Toll Collection (ETC) operations for major roads and highways.'
  },
  {
    year: '2015',
    title: 'Expansion into Ship Building',
    description: 'Diversified operations into shipbuilding, carrier operation, and navigation through sister concerns.'
  },
  {
    year: 'Present',
    title: '80% Market Share',
    description: 'ATT and its associates now enjoy about 80% of the total market share in their core business sectors.'
  }
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
