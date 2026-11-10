<template>
  <footer class="bg-brand-950 pt-16 pb-8">
    <div class="px-5 mx-auto max-w-7xl">

      <!-- Top row: logo + nav -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-10 pb-12 border-b border-white/10">

        <!-- Brand column -->
        <div class="lg:col-span-2">
          <NuxtImg
            src="/images/logo-dark-cropped.png"
            alt="ADTEKO Pty Ltd"
            height="64"
            class="h-16 w-auto mb-5"
          />
          <p class="font-body text-sm text-white/45 leading-relaxed max-w-xs">
            BIM &amp; 3D visualisation, building &amp; farming supplies, and project &amp; contract management across Australia.
          </p>
          <div v-if="abn" class="mt-5 font-body text-xs text-white/30">
            ABN: {{ abn }}
          </div>
        </div>

        <!-- Services column -->
        <div>
          <div class="font-display text-xs font-bold uppercase tracking-[0.15em] text-white/50 mb-5">
            Divisions
          </div>
          <ul class="space-y-3">
            <li v-for="service in footerServices" :key="service">
              <a href="/#services"
                 class="font-body text-sm text-white/40 hover:text-white/80 transition-colors">
                {{ service }}
              </a>
            </li>
          </ul>
        </div>

        <!-- Navigation column -->
        <div>
          <div class="font-display text-xs font-bold uppercase tracking-[0.15em] text-white/50 mb-5">
            Navigation
          </div>
          <ul class="space-y-3">
            <li v-for="item in navLinks" :key="item.label">
              <a :href="item.href"
                 class="font-body text-sm text-white/40 hover:text-white/80 transition-colors">
                {{ item.label }}
              </a>
            </li>
          </ul>
        </div>

      </div>

      <!-- Bottom row: copyright -->
      <div class="pt-8 flex flex-col sm:flex-row items-center justify-between gap-4">
        <p class="font-body text-xs text-white/30">
          &copy; {{ currentYear }} ADTEKO Pty Ltd. All rights reserved.
        </p>
        <p class="font-body text-xs text-white/20">
          Coffs Harbour, NSW — Serving Australia-Wide ·
          <NuxtLink to="/privacy" class="hover:text-white/60 transition-colors">Privacy Policy</NuxtLink>
        </p>
      </div>

    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear()
// Set the ABN here (e.g. '12 345 678 901'); the line stays hidden while empty.
const abn = '12 695 996 073'

const footerServices = [
  'BIM & 3D Visualisation',
  'Building & Farming Supplies',
  'Project & Contract Management',
]

const navLinks = [
  { label: 'Home', href: '/#home' },
  { label: 'Divisions', href: '/#services' },
  { label: 'About', href: '/#about' },
  { label: 'Contact', href: '/#contact' },
]
</script>
