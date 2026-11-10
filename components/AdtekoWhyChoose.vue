<template>
  <section class="relative py-24 lg:py-32 overflow-hidden" style="background-color: #5C1A4E;">
    <!-- Subtle background grid -->
    <div
      class="absolute inset-0 pointer-events-none"
      style="
        background-image:
          linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px),
          linear-gradient(to right, rgba(255,255,255,0.04) 1px, transparent 1px);
        background-size: 72px 72px;
      "
    ></div>

    <div class="relative px-5 mx-auto max-w-7xl">

      <!-- Section header -->
      <div class="flex items-center gap-4 mb-4">
        <div class="h-px w-8 bg-white/30"></div>
        <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-white/50">
          Our Commitment
        </span>
      </div>
      <h2 class="font-display font-bold text-white uppercase leading-tight mb-16"
          style="font-size: clamp(2rem, 4vw, 3rem);">
        Why Choose ADTEKO
      </h2>

      <!-- Pillars grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-px bg-white/10">
        <div
          v-for="(pillar, index) in pillars"
          :key="pillar.title"
          class="bg-brand-800/50 hover:bg-brand-800/80 transition-colors duration-300 p-8 lg:p-6 xl:p-8 group"
        >
          <!-- Number -->
          <div class="font-display text-5xl font-bold text-white/10 group-hover:text-white/15 leading-none mb-4 transition-colors">
            {{ String(index + 1).padStart(2, '0') }}
          </div>

          <!-- Thin line -->
          <div class="w-8 h-px bg-white/30 mb-5"></div>

          <!-- Title -->
          <h3 class="font-display text-base font-bold uppercase tracking-wide text-white leading-tight mb-3">
            {{ pillar.title }}
          </h3>

          <!-- Description -->
          <p class="font-body text-sm text-white/55 leading-relaxed group-hover:text-white/70 transition-colors">
            {{ pillar.description }}
          </p>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const pillars = [
  {
    title: 'Advanced Thinking',
    description: 'We apply rigorous engineering analysis to identify the most effective approach for each unique situation.',
  },
  {
    title: 'Fit-for-Purpose Solutions',
    description: 'No over-engineering. Every recommendation is sized and scoped to match your actual project requirements.',
  },
  {
    title: 'Integrity',
    description: 'Honest assessments, clear reporting, and advice you can rely on — even when it means saying the harder thing.',
  },
  {
    title: 'Efficiency',
    description: 'We streamline processes, reduce administrative overhead, and keep projects progressing on schedule.',
  },
  {
    title: 'Reliability',
    description: 'Consistent delivery, responsive communication, and dependable support throughout the project lifecycle.',
  },
]
</script>
