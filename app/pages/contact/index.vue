<template>
  <div>
    <PageHero
      title="Contact Us"
      subtitle="Get in touch with our team for project consultations, product enquiries, or technical support. We'd love to hear from you."
      label="Get In Touch"
    />

    <section class="py-20 bg-slate-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-10">

          <!-- Contact Info Cards -->
          <div class="space-y-5">
            <div v-for="info in contactInfo" :key="info.label" class="bg-white rounded-2xl border border-slate-100 p-6 shadow-sm hover:shadow-lg transition-all duration-300 hover:-translate-y-0.5">
              <div :class="['w-12 h-12 rounded-xl flex items-center justify-center text-white mb-4 bg-gradient-to-br', info.color]">
                <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" :d="info.icon" />
                </svg>
              </div>
              <div class="text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">{{ info.label }}</div>
              <div v-for="line in info.lines" :key="line">
                <a v-if="info.href" :href="`${info.href}${line}`" class="text-slate-800 font-medium hover:text-blue-600 transition-colors block text-sm">{{ line }}</a>
                <p v-else class="text-slate-800 font-medium text-sm">{{ line }}</p>
              </div>
            </div>

            <!-- Map placeholder -->
            <div class="bg-primary-900 rounded-2xl p-6 text-white">
              <div class="text-xs font-semibold text-white/50 uppercase tracking-wider mb-2">Location</div>
              <p class="text-sm text-white/80 leading-relaxed mb-4">House #67, Road #27, Gulshan Circle #1, Dhaka-1212, Bangladesh</p>
              <a
                href="https://maps.google.com/?q=Gulshan+Circle+1+Dhaka+Bangladesh"
                target="_blank"
                rel="noopener"
                class="inline-flex items-center gap-2 text-accent-400 text-sm font-semibold hover:text-accent-300 transition-colors"
              >
                <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z"/><path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z"/></svg>
                View on Google Maps
              </a>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="lg:col-span-2">
            <div class="bg-white rounded-2xl border border-slate-100 shadow-sm p-8 md:p-10">
              <div class="mb-8">
                <div class="inline-flex items-center gap-2 px-3 py-1.5 bg-blue-50 text-blue-700 text-xs font-semibold rounded-full border border-blue-100 mb-4">
                  Send us a Message
                </div>
                <h2 class="text-2xl font-bold text-slate-900 mb-2">How can we help you?</h2>
                <p class="text-slate-500 text-sm">Fill in the form below and our team will get back to you within 1 business day.</p>
              </div>

              <form @submit.prevent="submitForm" class="space-y-5">
                <div class="grid sm:grid-cols-2 gap-5">
                  <div>
                    <label class="form-label" for="name">Full Name *</label>
                    <input id="name" v-model="form.name" type="text" class="form-input" placeholder="Your full name" required />
                  </div>
                  <div>
                    <label class="form-label" for="email">Email Address *</label>
                    <input id="email" v-model="form.email" type="email" class="form-input" placeholder="your@email.com" required />
                  </div>
                </div>

                <div class="grid sm:grid-cols-2 gap-5">
                  <div>
                    <label class="form-label" for="phone">Phone Number</label>
                    <input id="phone" v-model="form.phone" type="tel" class="form-input" placeholder="+88 01XXX XXX XXX" />
                  </div>
                  <div>
                    <label class="form-label" for="subject">Subject *</label>
                    <select id="subject" v-model="form.subject" class="form-input" required>
                      <option value="" disabled>Select a subject</option>
                      <option>Solution Inquiry</option>
                      <option>Product Inquiry</option>
                      <option>Service Request</option>
                      <option>Project Discussion</option>
                      <option>Maintenance Support</option>
                      <option>General Inquiry</option>
                    </select>
                  </div>
                </div>

                <div>
                  <label class="form-label" for="company">Organization / Company</label>
                  <input id="company" v-model="form.company" type="text" class="form-input" placeholder="Your organization name" />
                </div>

                <div>
                  <label class="form-label" for="message">Message *</label>
                  <textarea id="message" v-model="form.message" class="form-input min-h-[140px] resize-none" placeholder="Please describe your requirements in detail..." required></textarea>
                </div>

                <!-- Success message -->
                <Transition name="dropdown">
                  <div v-if="submitted" class="flex items-center gap-3 p-4 bg-green-50 border border-green-200 rounded-xl text-green-700 text-sm font-medium">
                    <svg class="w-5 h-5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                    Thank you! Your message has been sent. We'll be in touch shortly.
                  </div>
                </Transition>

                <button
                  type="submit"
                  :disabled="submitting"
                  class="w-full sm:w-auto px-10 py-4 bg-primary-700 hover:bg-primary-600 disabled:opacity-60 text-white font-bold rounded-xl transition-all duration-200 hover:scale-105 shadow-lg flex items-center justify-center gap-2"
                >
                  <svg v-if="submitting" class="w-4 h-4 animate-spin" fill="none" viewBox="0 0 24 24"><circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"/><path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4z"/></svg>
                  {{ submitting ? 'Sending...' : 'Send Message' }}
                  <svg v-if="!submitting" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5"/></svg>
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'Contact Us — ATT | Asian Traffic Technologies Ltd',
  description: 'Contact Asian Traffic Technologies Ltd for ITS solutions, product inquiries, project consultations, and technical support. Based in Dhaka, Bangladesh.',
})

const form = reactive({
  name: '',
  email: '',
  phone: '',
  company: '',
  subject: '',
  message: '',
})

const submitting = ref(false)
const submitted = ref(false)

async function submitForm() {
  submitting.value = true
  // Simulate API call
  await new Promise(r => setTimeout(r, 1200))
  submitting.value = false
  submitted.value = true
  // Reset form
  Object.assign(form, { name: '', email: '', phone: '', company: '', subject: '', message: '' })
  setTimeout(() => { submitted.value = false }, 6000)
}

const contactInfo = [
  {
    label: 'Phone',
    icon: 'M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z',
    color: 'from-blue-500 to-blue-700',
    href: 'tel:',
    lines: ['+88-2-8832313', '+88-2-8832240'],
  },
  {
    label: 'Email',
    icon: 'M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75',
    color: 'from-accent-500 to-orange-600',
    href: 'mailto:',
    lines: ['info@att-bd.com'],
  },
  {
    label: 'Office Address',
    icon: 'M15 10.5a3 3 0 11-6 0 3 3 0 016 0z M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z',
    color: 'from-green-500 to-emerald-700',
    href: null,
    lines: ['House #67, Road #27,', 'Gulshan Circle #1,', 'Dhaka-1212, Bangladesh'],
  },
]
</script>

<style scoped>
.form-label {
  display: block;
  font-size: 0.8125rem;
  font-weight: 600;
  color: #374151;
  margin-bottom: 0.375rem;
}

.form-input {
  width: 100%;
  padding: 0.75rem 1rem;
  border: 1.5px solid #e2e8f0;
  border-radius: 0.75rem;
  font-size: 0.875rem;
  color: #1e293b;
  background: #f8fafc;
  outline: none;
  transition: all 0.2s;
}

.form-input:focus {
  border-color: #2563eb;
  background: #fff;
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
}

.form-input::placeholder {
  color: #94a3b8;
}
</style>
