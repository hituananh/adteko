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
      </div>

      <!-- Divisions grid: one critical line per card; click opens details -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-px bg-brand-200">
        <button
          v-for="(division, index) in divisions"
          :key="division.title"
          type="button"
          :aria-label="`View details: ${division.title}`"
          :class="[
            'text-left bg-white p-8 lg:p-10 group hover:bg-brand-700 transition-colors duration-300 flex flex-col cursor-pointer focus:outline-none focus-visible:ring-2 focus-visible:ring-brand-700',
            index === 2 ? 'md:col-span-2 lg:col-span-1' : ''
          ]"
          @click="open(index)"
        >
          <div class="flex items-start justify-between mb-6 w-full">
            <span class="font-display text-4xl font-bold text-brand-200 group-hover:text-white/20 transition-colors leading-none">
              {{ String(index + 1).padStart(2, '0') }}
            </span>
            <div class="w-8 h-8 border border-brand-200 group-hover:border-white/30 flex items-center justify-center transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" class="text-brand-400 group-hover:text-white/50 transition-colors">
                <path stroke-linecap="square" d="M12 5v14M5 12h14"/>
              </svg>
            </div>
          </div>
          <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-400 group-hover:text-white/50 mb-2 transition-colors">
            {{ division.label }}
          </span>
          <h3 class="font-display text-lg font-bold uppercase tracking-wide text-brand-900 group-hover:text-white mb-4 transition-colors leading-tight">
            {{ division.title }}
          </h3>
          <p class="font-body text-sm text-stone-500 group-hover:text-white/75 mb-8 leading-relaxed transition-colors">
            {{ division.tagline }}
          </p>
          <span class="mt-auto font-display text-xs font-semibold uppercase tracking-[0.2em] text-brand-700 group-hover:text-white transition-colors">
            View details +
          </span>
        </button>
      </div>
    </div>

    <!-- Details popup -->
    <Teleport to="body">
      <Transition
        enter-active-class="transition-opacity duration-200"
        enter-from-class="opacity-0"
        leave-active-class="transition-opacity duration-150"
        leave-to-class="opacity-0"
      >
        <div
          v-if="active"
          class="fixed inset-0 z-[60] flex items-center justify-center p-4 sm:p-6 bg-brand-950/70 backdrop-blur-sm"
          @click.self="close"
        >
          <div
            role="dialog"
            aria-modal="true"
            :aria-labelledby="`division-title-${activeIndex}`"
            class="relative w-full max-w-xl max-h-[90vh] overflow-y-auto bg-white shadow-2xl"
          >
            <!-- Header strip in brand plum -->
            <div class="px-8 pt-8 pb-6" style="background-color: #5C1A4E;">
              <button
                type="button"
                aria-label="Close"
                class="absolute top-4 right-4 w-9 h-9 flex items-center justify-center border border-white/30 text-white/70 hover:text-white hover:border-white transition-colors"
                @click="close"
              >
                <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="square" d="M6 6l12 12M18 6L6 18"/>
                </svg>
              </button>
              <span class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-white/50">
                {{ active.label }}
              </span>
              <h3
                :id="`division-title-${activeIndex}`"
                class="font-display text-2xl font-bold uppercase tracking-wide text-white mt-2 leading-tight pr-10"
              >
                {{ active.title }}
              </h3>
            </div>

            <div class="px-8 py-8">
              <p class="font-body text-stone-600 leading-relaxed mb-6">
                {{ active.summary }}
              </p>
              <ul class="space-y-3 mb-10">
                <li v-for="point in active.points" :key="point"
                    class="flex items-start gap-3 font-body text-sm text-stone-600">
                  <span class="mt-1.5 w-1.5 h-1.5 rounded-full bg-brand-700 shrink-0"></span>
                  {{ point }}
                </li>
              </ul>

              <!-- Action buttons -->
              <div class="flex flex-wrap gap-4">
                <a
                  :href="active.href"
                  class="inline-block px-8 py-4 font-display text-sm font-semibold uppercase tracking-[0.12em] text-white bg-brand-700 hover:bg-brand-800 transition-colors duration-200"
                  @click="close"
                >
                  {{ active.cta }} &rarr;
                </a>
                <button
                  type="button"
                  class="inline-block px-8 py-4 font-display text-sm font-semibold uppercase tracking-[0.12em] text-brand-700 border border-brand-200 hover:border-brand-700 transition-colors duration-200"
                  @click="close"
                >
                  Close
                </button>
              </div>
            </div>
          </div>
        </div>
      </Transition>
    </Teleport>
  </section>
</template>

<script setup>
// When the niche websites go live, replace each href with the niche domain
// (e.g. 'https://<bim-brand>.com.au') — see Claude_Office website plan.
const divisions = [
  {
    label: 'Division 01',
    title: 'BIM & 3D Visualisation',
    tagline: 'Built on the Autodesk ecosystem with licensed software and an experienced BIM team.',
    summary:
      'We work end to end in the Autodesk ecosystem, using fully licensed Revit, AutoCAD and Navisworks. Our experienced BIM team turns your 2D drawings into accurate 3D models, renders, shop drawings and take-offs, ready for landlord approval, fabrication and construction, in native formats your consultants can open and reuse.',
    points: [
      'Licensed Autodesk Revit, AutoCAD and Navisworks',
      'Experienced BIM modellers and detailers',
      'Tenancy design-approval render packs',
      'Franchise roll-out visualisation',
      '2D CAD to 3D / BIM modelling',
      'Shop drawings and steel detailing',
      'Quantity take-off',
      'Clash check and coordination (Navisworks)',
    ],
    cta: 'Enquire about BIM',
    href: '/#contact',
  },
  {
    label: 'Division 02',
    title: 'Building & Farming Supplies',
    tagline: 'Direct-import building and farming supplies, quality-checked at the factory before they ship.',
    summary:
      'Direct-import building materials and agricultural structures, sourced and quality-checked at the factory and delivered across NSW and QLD.',
    points: [
      'Shade cloth, weed mat and farm supplies',
      'Greenhouses and tunnel farming systems',
      'Building and construction materials',
      'Factory QC, logistics and import coordination',
    ],
    cta: 'Request a quote',
    href: '/#contact',
  },
  {
    label: 'Division 03',
    title: 'Project & Contract Management',
    tagline: 'Your project, contracts and tenders managed directly by our founder.',
    summary:
      'Work directly with our founder to run your project, contracts and tenders, from scope clarification to final handover.',
    points: [
      'Project management',
      'Contract management and administration',
      'Tender management and bid preparation',
    ],
    cta: 'Talk to our founder',
    href: '/#contact',
  },
]

const activeIndex = ref(null)
const active = computed(() => (activeIndex.value === null ? null : divisions[activeIndex.value]))

function open(index) {
  activeIndex.value = index
}
function close() {
  activeIndex.value = null
}

function onKey(e) {
  if (e.key === 'Escape') close()
}

watch(activeIndex, (val) => {
  if (import.meta.client) document.body.style.overflow = val === null ? '' : 'hidden'
})

onMounted(() => window.addEventListener('keydown', onKey))
onUnmounted(() => {
  window.removeEventListener('keydown', onKey)
  document.body.style.overflow = ''
})
</script>
