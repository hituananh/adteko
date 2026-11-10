<script setup>
const isMenuOpen = ref(false)
const isScrolled = ref(false)

onMounted(() => {
  const onScroll = () => { isScrolled.value = window.scrollY > 20 }
  window.addEventListener('scroll', onScroll, { passive: true })
  onUnmounted(() => window.removeEventListener('scroll', onScroll))
})

const navItems = [
  { label: 'Home', href: '/#home' },
  { label: 'Divisions', href: '/#services' },
  { label: 'About', href: '/#about' },
  { label: 'Contact', href: '/#contact' },
]
</script>

<template>
  <header
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
      isScrolled
        ? 'bg-white/96 backdrop-blur-md border-b border-brand-100 shadow-sm'
        : 'bg-white border-b border-brand-100/60'
    ]"
  >
    <div class="px-5 mx-auto max-w-7xl">
      <div class="flex items-center justify-between h-20">
        <!-- Logo -->
        <a href="/#home" class="flex items-center shrink-0">
          <NuxtImg
            src="/images/logo-light-cropped.png"
            alt="ADTEKO Pty Ltd"
            height="64"
            class="h-14 md:h-16 w-auto"
          />
        </a>

        <!-- Desktop navigation -->
        <nav class="hidden md:flex items-center gap-8">
          <a
            v-for="item in navItems"
            :key="item.label"
            :href="item.href"
            class="font-display text-sm font-semibold uppercase tracking-[0.12em] text-stone-500 hover:text-brand-700 transition-colors duration-200"
          >
            {{ item.label }}
          </a>
          <a
            href="/#contact"
            class="px-6 py-2.5 font-display text-sm font-semibold uppercase tracking-[0.12em] text-white bg-brand-700 hover:bg-brand-800 transition-colors duration-200"
          >
            Get in Touch
          </a>
        </nav>

        <!-- Mobile hamburger -->
        <button
          @click="isMenuOpen = !isMenuOpen"
          class="md:hidden p-2 text-brand-700"
          aria-label="Toggle menu"
        >
          <svg v-if="!isMenuOpen" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="square" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="square" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile navigation drawer -->
    <Transition
      enter-active-class="transition-all duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div v-if="isMenuOpen" class="md:hidden bg-white border-t border-brand-100">
        <div class="px-5 py-6 flex flex-col gap-5">
          <a
            v-for="item in navItems"
            :key="item.label"
            :href="item.href"
            @click="isMenuOpen = false"
            class="font-display text-sm font-semibold uppercase tracking-[0.12em] text-stone-600 hover:text-brand-700 transition-colors"
          >
            {{ item.label }}
          </a>
          <a
            href="/#contact"
            @click="isMenuOpen = false"
            class="text-center px-6 py-3 font-display text-sm font-semibold uppercase tracking-[0.12em] text-white bg-brand-700 hover:bg-brand-800 transition-colors"
          >
            Get in Touch
          </a>
        </div>
      </div>
    </Transition>
  </header>
</template>
