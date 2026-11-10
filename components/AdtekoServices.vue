<template>
  <section id="services" class="py-24 lg:py-32 bg-brand-50">
    <div class="px-5 mx-auto max-w-7xl">

      <!-- Section header -->
      <div class="max-w-2xl mb-16">
        <div class="flex items-center gap-4 mb-6">
          <div class="h-px w-8 bg-brand-700"></div>
          <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-700">
            What We Do
          </span>
        </div>
        <h2 class="font-display font-bold text-brand-900 uppercase leading-tight"
            style="font-size: clamp(2rem, 4vw, 3rem);">
          Our Services
        </h2>
        <p class="font-body text-stone-500 mt-4 leading-relaxed">
          From technical assessments to procurement and project management, ADTEKO delivers
          targeted expertise across five core service areas.
        </p>
      </div>

      <!-- Services grid: 2 large + 3 smaller -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-px bg-brand-200">

        <!-- Service 01 -->
        <div class="bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300 md:col-span-2 lg:col-span-1">
          <div class="flex items-start justify-between mb-6">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">01</span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M7 17L17 7M17 7H7M17 7v10"/>
              </svg>
            </div>
          </div>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            Technical Consulting &amp; Engineering Advisory
          </h3>
          <ul class="space-y-2">
            <li v-for="point in services[0].points" :key="point"
                class="flex items-start gap-2 font-body text-sm text-stone-500 group-hover:text-white/65 transition-colors">
              <span class="mt-1.5 w-1 h-1 rounded-full bg-brand-400 group-hover:bg-white/40 shrink-0 transition-colors"></span>
              {{ point }}
            </li>
          </ul>
        </div>

        <!-- Service 02 -->
        <div class="bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300">
          <div class="flex items-start justify-between mb-6">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">02</span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M7 17L17 7M17 7H7M17 7v10"/>
              </svg>
            </div>
          </div>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            Steel Detailing &amp; Drafting
          </h3>
          <ul class="space-y-2">
            <li v-for="point in services[1].points" :key="point"
                class="flex items-start gap-2 font-body text-sm text-stone-500 group-hover:text-white/65 transition-colors">
              <span class="mt-1.5 w-1 h-1 rounded-full bg-brand-400 group-hover:bg-white/40 shrink-0 transition-colors"></span>
              {{ point }}
            </li>
          </ul>
        </div>

        <!-- Service 03 -->
        <div class="bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300">
          <div class="flex items-start justify-between mb-6">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">03</span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M7 17L17 7M17 7H7M17 7v10"/>
              </svg>
            </div>
          </div>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            Project Management Support
          </h3>
          <ul class="space-y-2">
            <li v-for="point in services[2].points" :key="point"
                class="flex items-start gap-2 font-body text-sm text-stone-500 group-hover:text-white/65 transition-colors">
              <span class="mt-1.5 w-1 h-1 rounded-full bg-brand-400 group-hover:bg-white/40 shrink-0 transition-colors"></span>
              {{ point }}
            </li>
          </ul>
        </div>

        <!-- Service 04 -->
        <div class="bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300">
          <div class="flex items-start justify-between mb-6">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">04</span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M7 17L17 7M17 7H7M17 7v10"/>
              </svg>
            </div>
          </div>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            Cross-Border Procurement &amp; Trading
          </h3>
          <ul class="space-y-2">
            <li v-for="point in services[3].points" :key="point"
                class="flex items-start gap-2 font-body text-sm text-stone-500 group-hover:text-white/65 transition-colors">
              <span class="mt-1.5 w-1 h-1 rounded-full bg-brand-400 group-hover:bg-white/40 shrink-0 transition-colors"></span>
              {{ point }}
            </li>
          </ul>
        </div>

        <!-- Service 05 -->
        <div class="bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300">
          <div class="flex items-start justify-between mb-6">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">05</span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M7 17L17 7M17 7H7M17 7v10"/>
              </svg>
            </div>
          </div>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            Greenhouse / Tunnel Solutions
          </h3>
          <ul class="space-y-2">
            <li v-for="point in services[4].points" :key="point"
                class="flex items-start gap-2 font-body text-sm text-stone-500 group-hover:text-white/65 transition-colors">
              <span class="mt-1.5 w-1 h-1 rounded-full bg-brand-400 group-hover:bg-white/40 shrink-0 transition-colors"></span>
              {{ point }}
            </li>
          </ul>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    points: [
      'Technical assessments',
      'Fit-for-purpose recommendations',
      'Material & specification advisory',
    ],
  },
  {
    points: [
      'Shop drawings',
      'Fabrication & erection drawings',
      'Outsourced detailing for Australian firms',
    ],
  },
  {
    points: [
      'Scope clarification (Civil, DRFA, Earthworks)',
      'Progress & quantity monitoring',
      'DRFA documentation support',
      'Earthworks coordination assistance',
    ],
  },
  {
    points: [
      'Sourcing from Vietnam & China',
      'Factory quality control',
      'Logistics & import coordination',
    ],
  },
  {
    points: [
      'Agricultural tunnels',
      'Custom sizing & specifications',
      'Import & delivery management',
    ],
  },
]
</script>
