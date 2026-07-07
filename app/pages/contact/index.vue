<template>
  <main class="bg-slate-950 min-h-screen">
    <PageHero
      title="Contact Us"
      subtitle="Get in touch with our team for project consultations, product enquiries, or technical support. We'd love to hear from you."
      label="Get In Touch"
    />

    <section class="py-24 bg-slate-950 border-t border-white/5">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-3 gap-12">

          <!-- Contact Info Cards -->
          <div class="space-y-6">
            <div v-for="info in contactInfo" :key="info.label" :class="['bg-slate-900/50 backdrop-blur-md border border-white/5 border-l-[4px] p-8 rounded-2xl shadow-xl hover:border-white/20 transition-all', info.color]">
              <div class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-4">{{ info.label }}</div>
              
              <!-- Address -->
              <div v-if="info.address" class="flex items-start gap-3 mb-4">
                <svg class="w-5 h-5 text-slate-400 flex-shrink-0 mt-1" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" /><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" /></svg>
                <p class="text-slate-300 font-medium text-sm leading-relaxed whitespace-pre-line">{{ info.address }}</p>
              </div>

              <!-- Phones -->
              <div v-if="info.phones && info.phones.length" class="flex items-start gap-3 mb-4">
                <svg class="w-5 h-5 text-slate-400 flex-shrink-0 mt-1" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" /></svg>
                <div>
                  <a v-for="phone in info.phones" :key="phone" :href="`tel:${phone.replace(/\s+/g, '')}`" class="text-white font-bold hover:text-accent-400 transition-colors block text-sm mb-1">Cell: {{ phone }}</a>
                </div>
              </div>

              <!-- Emails -->
              <div v-if="info.emails && info.emails.length" class="flex items-start gap-3 mb-4">
                <svg class="w-5 h-5 text-slate-400 flex-shrink-0 mt-1" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" /></svg>
                <div>
                  <a v-for="email in info.emails" :key="email" :href="`mailto:${email}`" class="text-white font-bold hover:text-accent-400 transition-colors block text-sm mb-1">{{ email }}</a>
                </div>
              </div>

              <!-- Web -->
              <div v-if="info.web" class="flex items-start gap-3">
                <svg class="w-5 h-5 text-slate-400 flex-shrink-0 mt-1" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" /></svg>
                <a :href="`https://${info.web}`" target="_blank" rel="noopener noreferrer" class="text-white font-bold hover:text-accent-400 transition-colors block text-sm">{{ info.web }}</a>
              </div>
            </div>


          </div>

          <!-- Contact Form -->
          <div class="lg:col-span-2">
            <div class="bg-slate-900/50 backdrop-blur-md rounded-3xl border border-white/5 shadow-2xl p-8 md:p-12">
              <div class="mb-10 border-l-[4px] border-accent-500 pl-6">
                <div class="text-[10px] font-bold text-accent-500 uppercase tracking-widest mb-3">Send us a Message</div>
                <h2 class="text-3xl md:text-4xl font-black text-white mb-4 uppercase tracking-wide leading-tight">How can we help you?</h2>
                <p class="text-slate-400 text-sm leading-relaxed">Fill in the form below and our team will get back to you within 1 business day.</p>
              </div>

              <form @submit.prevent="submitForm" class="space-y-6">
                <div class="grid sm:grid-cols-2 gap-6">
                  <div>
                    <label class="form-label" for="name">Full Name *</label>
                    <input id="name" v-model="form.name" type="text" class="form-input" placeholder="Your full name" required />
                  </div>
                  <div>
                    <label class="form-label" for="email">Email Address *</label>
                    <input id="email" v-model="form.email" type="email" class="form-input" placeholder="your@email.com" required />
                  </div>
                </div>

                <div class="grid sm:grid-cols-2 gap-6">
                  <div>
                    <label class="form-label" for="phone">Phone Number</label>
                    <input id="phone" v-model="form.phone" type="tel" class="form-input" placeholder="+88 01XXX XXX XXX" />
                  </div>
                  <div>
                    <label class="form-label" for="subject">Subject *</label>
                    <select id="subject" v-model="form.subject" class="form-input" required>
                      <option value="" disabled class="bg-slate-800">Select a subject</option>
                      <option class="bg-slate-800">Solution Inquiry</option>
                      <option class="bg-slate-800">Product Inquiry</option>
                      <option class="bg-slate-800">Service Request</option>
                      <option class="bg-slate-800">Project Discussion</option>
                      <option class="bg-slate-800">Maintenance Support</option>
                      <option class="bg-slate-800">General Inquiry</option>
                    </select>
                  </div>
                </div>

                <div>
                  <label class="form-label" for="company">Organization / Company</label>
                  <input id="company" v-model="form.company" type="text" class="form-input" placeholder="Your organization name" />
                </div>

                <div>
                  <label class="form-label" for="message">Message *</label>
                  <textarea id="message" v-model="form.message" class="form-input min-h-[160px] resize-none" placeholder="Please describe your requirements in detail..." required></textarea>
                </div>

                <!-- Success message -->
                <Transition name="dropdown">
                  <div v-if="submitted" class="flex items-center gap-3 p-5 bg-green-500/10 border border-green-500/20 rounded-2xl text-green-400 text-sm font-bold">
                    <svg class="w-5 h-5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                    Thank you! Your message has been sent. We'll be in touch shortly.
                  </div>
                </Transition>

                <div class="pt-4">
                  <button
                    type="submit"
                    :disabled="submitting"
                    class="w-full sm:w-auto px-10 py-4 bg-white/10 hover:bg-white/20 border border-white/20 text-white disabled:opacity-60 font-bold uppercase tracking-widest rounded-full transition-all duration-300 flex items-center justify-center gap-3 group"
                  >
                    <svg v-if="submitting" class="w-5 h-5 animate-spin" fill="none" viewBox="0 0 24 24"><circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"/><path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4z"/></svg>
                    {{ submitting ? 'Sending...' : 'Send Message' }}
                    <svg v-if="!submitting" class="w-5 h-5 text-accent-500 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
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
    label: 'Head Office',
    color: 'border-l-blue-500',
    address: 'Asian Traffic Technologies Limited\nHouse # 67, Road # 27, Flat # 5A,\nGulshan Circle -1, Dhaka - 1212,\nBangladesh.',
    phones: ['+880 1811-860454', '+880 1728-795392'],
    emails: ['info@att-bd.com', 'shamsnavigation@att-bd.com'],
    web: 'www.att-bd.com'
  },
  {
    label: 'Registered Office',
    color: 'border-l-accent-500',
    address: 'House-5/1/M, Mohonpur, Ring\nRoad, Shamoly, Dhaka-1207,\nBangladesh',
    phones: [],
    emails: ['info@att-bd.com', 'shamsnavigation@att-bd.com'],
    web: 'www.att-bd.com'
  },
  {
    label: 'Chattogram Office',
    color: 'border-l-slate-500',
    address: '37, Kaderi Chamber (4th Floor),\nAgrabad, Chattogram,\nBangladesh',
    phones: ['+880 1717-271844'],
    emails: [],
    web: ''
  },
]
</script>

<style scoped>
.form-label {
  display: block;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: #94a3b8; /* slate-400 */
  margin-bottom: 0.5rem;
}

.form-input {
  width: 100%;
  padding: 1rem 1.25rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
  font-size: 0.875rem;
  color: #ffffff;
  background: rgba(255, 255, 255, 0.05);
  outline: none;
  transition: all 0.3s;
}

.form-input:focus {
  border-color: var(--color-accent-500);
  background: rgba(255, 255, 255, 0.1);
  box-shadow: 0 0 0 4px rgba(6, 182, 212, 0.1);
}

.form-input::placeholder {
  color: #64748b; /* slate-500 */
}
</style>
