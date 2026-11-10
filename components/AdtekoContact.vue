<template>
  <section id="contact" class="py-24 lg:py-32 bg-white">
    <div class="px-5 mx-auto max-w-7xl">

      <!-- Section header -->
      <div class="flex items-center gap-4 mb-6">
        <div class="h-px w-8 bg-brand-700"></div>
        <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-700">
          Get in Touch
        </span>
      </div>
      <h2 class="font-display font-bold text-brand-900 uppercase leading-tight mb-16"
          style="font-size: clamp(2rem, 4vw, 3rem);">
        Contact ADTEKO
      </h2>

      <div class="grid lg:grid-cols-2 gap-16 lg:gap-24">

        <!-- Left: Contact form -->
        <div>
          <!-- Success message -->
          <div
            v-if="formState === 'success'"
            class="p-8 bg-brand-50 border-l-4 border-brand-700"
          >
            <h3 class="font-display text-xl font-bold uppercase text-brand-800 mb-2">
              Message Received
            </h3>
            <p class="font-body text-stone-600">
              Thank you for reaching out. A member of the ADTEKO team will be in touch with you shortly.
            </p>
          </div>

          <!-- Error message -->
          <div
            v-else-if="formState === 'error'"
            class="p-6 mb-6 bg-red-50 border-l-4 border-red-500"
          >
            <p class="font-body text-sm text-red-700">
              There was an issue submitting your enquiry. Please try again or contact us directly by email.
            </p>
          </div>

          <!-- Contact form -->
          <form
            v-if="formState !== 'success'"
            name="adteko-contact"
            method="POST"
            data-netlify="true"
            netlify-honeypot="bot-field"
            @submit.prevent="handleSubmit"
            class="space-y-5"
          >
            <input type="hidden" name="form-name" value="adteko-contact" />
            <div style="display:none;">
              <label>Don't fill this out: <input name="bot-field" v-model="botField" /></label>
            </div>

            <!-- Name + Email row -->
            <div class="grid sm:grid-cols-2 gap-5">
              <div>
                <label class="block font-display text-xs font-semibold uppercase tracking-wider text-stone-500 mb-2">
                  Full Name <span class="text-brand-600">*</span>
                </label>
                <input
                  v-model="form.name"
                  name="name"
                  type="text"
                  required
                  placeholder="Your name"
                  class="w-full px-4 py-3 font-body text-sm border border-stone-200 focus:border-brand-700 focus:outline-none focus:ring-1 focus:ring-brand-700 transition-colors bg-white placeholder:text-stone-300"
                />
              </div>
              <div>
                <label class="block font-display text-xs font-semibold uppercase tracking-wider text-stone-500 mb-2">
                  Email Address <span class="text-brand-600">*</span>
                </label>
                <input
                  v-model="form.email"
                  name="email"
                  type="email"
                  required
                  placeholder="your@email.com"
                  class="w-full px-4 py-3 font-body text-sm border border-stone-200 focus:border-brand-700 focus:outline-none focus:ring-1 focus:ring-brand-700 transition-colors bg-white placeholder:text-stone-300"
                />
              </div>
            </div>

            <!-- Phone + Subject row -->
            <div class="grid sm:grid-cols-2 gap-5">
              <div>
                <label class="block font-display text-xs font-semibold uppercase tracking-wider text-stone-500 mb-2">
                  Phone Number
                </label>
                <input
                  v-model="form.phone"
                  name="phone"
                  type="tel"
                  placeholder="0400 000 000"
                  class="w-full px-4 py-3 font-body text-sm border border-stone-200 focus:border-brand-700 focus:outline-none focus:ring-1 focus:ring-brand-700 transition-colors bg-white placeholder:text-stone-300"
                />
              </div>
              <div>
                <label class="block font-display text-xs font-semibold uppercase tracking-wider text-stone-500 mb-2">
                  Subject
                </label>
                <select
                  v-model="form.subject"
                  name="subject"
                  class="w-full px-4 py-3 font-body text-sm border border-stone-200 focus:border-brand-700 focus:outline-none focus:ring-1 focus:ring-brand-700 transition-colors bg-white text-stone-600 appearance-none"
                >
                  <option value="" disabled>Select a division</option>
                  <option>BIM &amp; 3D Visualisation</option>
                  <option>Building &amp; Farming Supplies</option>
                  <option>Engineering &amp; Project Advisory</option>
                  <option>General Enquiry</option>
                </select>
              </div>
            </div>

            <!-- Message -->
            <div>
              <label class="block font-display text-xs font-semibold uppercase tracking-wider text-stone-500 mb-2">
                Message <span class="text-brand-600">*</span>
              </label>
              <textarea
                v-model="form.message"
                name="message"
                required
                rows="5"
                placeholder="Briefly describe your project or enquiry…"
                class="w-full px-4 py-3 font-body text-sm border border-stone-200 focus:border-brand-700 focus:outline-none focus:ring-1 focus:ring-brand-700 transition-colors bg-white placeholder:text-stone-300 resize-none"
              ></textarea>
            </div>

            <button
              type="submit"
              :disabled="formState === 'submitting'"
              class="px-8 py-4 font-display text-sm font-semibold uppercase tracking-[0.12em] text-white bg-brand-700 hover:bg-brand-800 disabled:opacity-60 disabled:cursor-not-allowed transition-colors duration-200 w-full sm:w-auto"
            >
              <span v-if="formState === 'submitting'">Sending…</span>
              <span v-else>Send Enquiry</span>
            </button>
          </form>
        </div>

        <!-- Right: Contact details -->
        <div class="space-y-10">
          <div>
            <h3 class="font-display text-sm font-bold uppercase tracking-wider text-brand-700 mb-5">
              Contact Details
            </h3>
            <div class="space-y-5">
              <div class="flex items-start gap-4">
                <div class="w-8 h-8 border border-brand-200 flex items-center justify-center shrink-0 mt-0.5">
                  <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-600">
                    <path stroke-linecap="square" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                  </svg>
                </div>
                <div>
                  <div class="font-display text-xs font-semibold uppercase tracking-wider text-stone-400 mb-1">Email</div>
                  <a href="mailto:contact@adteko.com.au" class="font-body text-stone-700 hover:text-brand-700 transition-colors">
                    contact@adteko.com.au
                  </a>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-8 h-8 border border-brand-200 flex items-center justify-center shrink-0 mt-0.5">
                  <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-600">
                    <path stroke-linecap="square" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                  </svg>
                </div>
                <div>
                  <div class="font-display text-xs font-semibold uppercase tracking-wider text-stone-400 mb-1">Phone</div>
                  <a href="tel:+61422178690" class="font-body text-stone-700 hover:text-brand-700 transition-colors">
                    0422 178 690
                  </a>
                </div>
              </div>


              <div class="flex items-start gap-4">
                <div class="w-8 h-8 border border-brand-200 flex items-center justify-center shrink-0 mt-0.5">
                  <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-600">
                    <path stroke-linecap="square" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                    <path stroke-linecap="square" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                  </svg>
                </div>
                <div>
                  <div class="font-display text-xs font-semibold uppercase tracking-wider text-stone-400 mb-1">Location</div>
                  <p class="font-body text-stone-700">Coffs Harbour, NSW, Australia</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Service area callout -->
          <div class="p-6 bg-brand-50 border-l-2 border-brand-700">
            <div class="font-display text-xs font-bold uppercase tracking-wider text-brand-700 mb-2">
              Service Area
            </div>
            <p class="font-body text-sm text-stone-600 leading-relaxed">
              ADTEKO provides services <strong class="text-stone-800">Australia-wide</strong>.
              Whether you're located in metro or regional areas, we are available to support
              your project from first drawing to final delivery.
            </p>
          </div>

          <!-- Response time note -->
          <div class="flex items-start gap-3 text-stone-400">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="mt-0.5 shrink-0">
              <path stroke-linecap="square" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/>
            </svg>
            <p class="font-body text-sm">
              Enquiries are typically responded to within 1–2 business days.
            </p>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const form = reactive({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: '',
})
const botField = ref('')
const formState = ref('idle') // idle | submitting | success | error

async function handleSubmit() {
  if (formState.value === 'submitting') return
  formState.value = 'submitting'

  try {
    const body = new URLSearchParams({
      'form-name': 'adteko-contact',
      'bot-field': botField.value,
      name: form.name,
      email: form.email,
      phone: form.phone,
      subject: form.subject,
      message: form.message,
    }).toString()

    const res = await fetch('/__forms.html', {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body,
    })

    if (res.ok) {
      formState.value = 'success'
    } else {
      formState.value = 'error'
    }
  } catch {
    formState.value = 'error'
  }
}
</script>
