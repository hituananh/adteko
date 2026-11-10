<template>
  <section id="about" class="py-24 lg:py-32 bg-white">
    <div class="px-5 mx-auto max-w-7xl">
      <div class="grid lg:grid-cols-2 gap-16 lg:gap-24 items-center">

        <!-- Left: Text content -->
        <div>
          <div class="flex items-center gap-4 mb-6">
            <div class="h-px w-8 bg-brand-700"></div>
            <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-700">
              About ADTEKO
            </span>
          </div>

          <h2 class="font-display font-bold text-brand-900 uppercase leading-tight mb-6"
              style="font-size: clamp(2rem, 4vw, 3rem);">
            Engineering Expertise.<br>
            Delivered with Integrity.
          </h2>

          <div class="space-y-4 font-body text-stone-600 leading-relaxed">
            <p>
              ADTEKO Pty Ltd is an Australian technical consulting and engineering firm
              providing practical, fit-for-purpose solutions to clients across a broad range
              of industries. Based in Coffs Harbour, NSW, we operate Australia-wide.
            </p>
            <p>
              Our team brings deep technical knowledge across engineering advisory, steel
              detailing, civil project management, cross-border procurement, and agricultural
              structures. We combine hands-on engineering experience with transparent communication
              to deliver measurable value on every engagement.
            </p>
            <p>
              Clients trust ADTEKO because we prioritise their project outcomes over
              inflated complexity. We cut through ambiguity, provide actionable recommendations,
              and stand behind our work.
            </p>
          </div>
        </div>

        <!-- Right: Strength pillars -->
        <div class="grid grid-cols-2 gap-4">
          <div
            v-for="(strength, index) in strengths"
            :key="strength.label"
            :class="[
              'p-6 border-l-2 border-brand-700 bg-brand-50',
              index === 0 ? 'col-span-2' : ''
            ]"
          >
            <div class="font-display text-3xl font-bold text-brand-700 leading-none mb-2">
              {{ strength.icon }}
            </div>
            <div class="font-display text-sm font-bold uppercase tracking-wider text-brand-900 mb-1">
              {{ strength.label }}
            </div>
            <p class="font-body text-xs text-stone-500 leading-relaxed">
              {{ strength.description }}
            </p>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const strengths = [
  {
    icon: '◈',
    label: 'Technical Insight',
    description: 'We bring deep domain knowledge across engineering disciplines, enabling informed decision-making at every project stage.',
  },
  {
    icon: '◧',
    label: 'Cost Efficiency',
    description: 'Practical recommendations that maximise value without unnecessary over-engineering.',
  },
  {
    icon: '◰',
    label: 'Reliability',
    description: 'Consistent delivery, transparent reporting, and accountable project management.',
  },
  {
    icon: '◱',
    label: 'Transparency',
    description: 'Open communication at every step — no surprises, no hidden agendas.',
  },
]
</script>
