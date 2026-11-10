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
          Our Divisions
        </h2>
        <p class="font-body text-stone-500 mt-4 leading-relaxed">
          ADTEKO operates through three focused divisions: BIM and 3D visualisation,
          building and farming supplies, and engineering advisory led by our founder.
        </p>
      </div>

      <!-- Divisions grid: 3 cards, same card style as before -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-px bg-brand-200">
        <a
          v-for="(division, index) in divisions"
          :key="division.title"
          :href="division.href"
          :class="[
            'bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300 flex flex-col',
            index === 2 ? 'md:col-span-2 lg:col-span-1' : ''
          ]"
        >
          <div class="flex items-start justify-between mb-6">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">
              {{ String(index + 1).padStart(2, '0') }}
            </span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M7 17L17 7M17 7H7M17 7v10"/>
              </svg>
            </div>
          </div>
          <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-400 group-hover:text-white/50 mb-2 transition-colors">
            {{ division.label }}
          </span>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            {{ division.title }}
          </h3>
          <p class="font-body text-sm text-stone-500 group-hover:text-white/65 mb-5 leading-relaxed transition-colors">
            {{ division.summary }}
          </p>
          <ul class="space-y-2 mb-8">
            <li v-for="point in division.points" :key="point"
                class="flex items-start gap-2 font-body text-sm text-stone-500 group-hover:text-white/65 transition-colors">
              <span class="mt-1.5 w-1 h-1 rounded-full bg-brand-400 group-hover:bg-white/40 shrink-0 transition-colors"></span>
              {{ point }}
            </li>
          </ul>
          <span class="mt-auto font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-700 group-hover:text-white transition-colors">
            {{ division.cta }} &rarr;
          </span>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
// When the niche websites go live, replace each href with the niche domain
// (e.g. 'https://<bim-brand>.com.au') — see Claude_Office website plan.
const divisions = [
  {
    label: 'Division 01',
    title: 'BIM & 3D Visualisation',
    summary:
      '3D models and photorealistic renders built from your 2D drawings, ready for landlord design approval, client sign-off and franchise roll-outs.',
    points: [
      'Tenancy design-approval render packs',
      'Franchise roll-out visualisation',
      '2D CAD to 3D / BIM modelling',
      'Coordination and clash review (Navisworks)',
    ],
    cta: 'Enquire about BIM',
    href: '#contact',
  },
  {
    label: 'Division 02',
    title: 'Building & Farming Supplies',
    summary:
      'Direct-import building materials and agricultural structures, sourced and quality-checked at the factory and delivered across NSW and QLD.',
    points: [
      'Shade cloth, weed mat and farm supplies',
      'Greenhouses and tunnel farming systems',
      'Building and construction materials',
      'Factory QC, logistics and import coordination',
    ],
    cta: 'Request a quote',
    href: '#contact',
  },
  {
    label: 'Division 03',
    title: 'Engineering & Project Advisory',
    summary:
      'Work directly with our founder on technical assessments, project management support and steel detailing for Australian projects.',
    points: [
      'Technical assessments and specification advice',
      'Project management support (civil, DRFA, earthworks)',
      'Steel detailing and shop drawings',
    ],
    cta: 'Talk to our founder',
    href: '#contact',
  },
]
</script>
