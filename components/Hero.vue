<template>
  <section
    id="home"
    class="relative min-h-screen flex items-center overflow-hidden"
    style="background-color: #5C1A4E;"
  >
    <!-- Engineering grid background -->
    <div
      class="absolute inset-0 pointer-events-none"
      style="
        background-image:
          linear-gradient(rgba(255,255,255,0.06) 1px, transparent 1px),
          linear-gradient(to right, rgba(255,255,255,0.06) 1px, transparent 1px);
        background-size: 72px 72px;
      "
    ></div>

    <!-- Subtle corner cross-hairs for technical feel -->
    <div class="absolute top-20 right-20 w-16 h-16 opacity-20 hidden lg:block">
      <div class="absolute top-1/2 left-0 right-0 h-px bg-white"></div>
      <div class="absolute left-1/2 top-0 bottom-0 w-px bg-white"></div>
    </div>
    <div class="absolute bottom-40 right-40 w-24 h-24 opacity-10 hidden xl:block">
      <div class="absolute top-1/2 left-0 right-0 h-px bg-white"></div>
      <div class="absolute left-1/2 top-0 bottom-0 w-px bg-white"></div>
      <div class="absolute inset-0 border border-white/40"></div>
    </div>

    <!-- Right panel: angular accent shape -->
    <div class="absolute top-0 right-0 bottom-0 w-96 hidden lg:block overflow-hidden pointer-events-none">
      <div
        class="absolute inset-0"
        style="background: rgba(255,255,255,0.04); clip-path: polygon(30% 0%, 100% 0%, 100% 100%, 0% 100%);"
      ></div>
      <div
        class="absolute inset-0"
        style="background: rgba(255,255,255,0.03); clip-path: polygon(50% 0%, 100% 0%, 100% 100%, 20% 100%);"
      ></div>
    </div>

    <!-- Main content -->
    <div class="relative z-10 w-full pt-28 pb-28 px-5 mx-auto max-w-7xl">
      <div class="max-w-2xl xl:max-w-3xl">

        <!-- Eyebrow label -->
        <div class="flex items-center gap-4 mb-10">
          <div class="h-px w-10 bg-white/30"></div>
          <span
            class="font-display text-xs font-semibold uppercase tracking-[0.25em] text-white/50"
          >
            BIM · Supplies · Engineering — Australia-Wide
          </span>
        </div>

        <!-- Main headline -->
        <h1
          class="font-display font-bold text-white leading-[0.92] uppercase"
          style="font-size: clamp(3.5rem, 10vw, 7.5rem);"
        >
          Advanced<br>
          <span style="color: rgba(255,255,255,0.28);">Thinking.</span><br>
          Advanced<br>
          Future.
        </h1>

        <!-- Separator line -->
        <div class="flex items-center gap-4 my-8">
          <div class="h-px w-16 bg-white/30"></div>
        </div>

        <!-- Subtext -->
        <div class="font-display text-xs font-semibold uppercase tracking-[0.2em] text-white/50 mb-3">
          Our Vision
        </div>
        <p class="text-base sm:text-lg font-body font-light text-white/75 max-w-xl leading-relaxed">
          To be the trusted right hand of every client we serve: guaranteeing the quality of every
          service and every product we deliver, and giving you the capacity to scale whenever you
          need to, without the risk.
        </p>

        <!-- CTA buttons -->
        <div class="flex flex-wrap gap-4 mt-10">
          <a
            href="/#contact"
            class="inline-block px-8 py-4 font-display text-sm font-semibold uppercase tracking-[0.12em] text-brand-700 bg-white hover:bg-brand-50 transition-colors duration-200"
          >
            Contact Us
          </a>
          <a
            href="/#services"
            class="inline-block px-8 py-4 font-display text-sm font-semibold uppercase tracking-[0.12em] text-white border border-white/40 hover:bg-white/10 hover:border-white/70 transition-colors duration-200"
          >
            Our Services
          </a>
        </div>

        <!-- Bottom stats strip -->
        <div class="flex flex-wrap gap-x-12 gap-y-4 mt-16 pt-10 border-t border-white/15">
          <div>
            <div class="font-display text-2xl font-bold text-white">3</div>
            <div class="font-body text-xs font-medium uppercase tracking-wider text-white/45 mt-0.5">Divisions</div>
          </div>
          <div>
            <div class="font-display text-2xl font-bold text-white">Australia-Wide</div>
            <div class="font-body text-xs font-medium uppercase tracking-wider text-white/45 mt-0.5">Service Coverage</div>
          </div>
          <div>
            <div class="font-display text-2xl font-bold text-white">NSW</div>
            <div class="font-body text-xs font-medium uppercase tracking-wider text-white/45 mt-0.5">Coffs Harbour HQ</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom wave transition -->
    <div class="absolute bottom-0 left-0 right-0 pointer-events-none">
      <svg
        viewBox="0 0 1440 64"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        class="w-full block"
        preserveAspectRatio="none"
      >
        <path d="M0 64L1440 0V64H0Z" fill="white"/>
      </svg>
    </div>
  </section>
</template>
