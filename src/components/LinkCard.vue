<template>
  <a
    href="#"
    target="_blank"
    rel="noopener noreferrer"
    class="group relative flex w-full items-center gap-4 rounded-xl border border-orange-900 bg-linear-to-br from-yellow-600 via-yellow-300 to-yellow-600 p-4 shadow-md shadow-gray-900/50 transition-all duration-300 hover:scale-[1.02] hover:border-orange-500 hover:shadow-xl hover:shadow-orange-950/20"
  >
    <!-- Icon Container -->
    <div
      class="rounden-lg flex h-12 w-12 shrink-0 items-center justify-center bg-yellow-600 text-yellow-900 transition-all duration-300 group-hover:scale-110 group-hover:bg-yellow-700 group-hover:text-white group-hover:shadow-xl group-hover:shadow-red-950/20"
    >
      <svg
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        class="h-6 w-6 transition-transform duration-300 group-hover:rotate-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 12v9a1 1 0 0 1-2 0V4c0-1.1.9-2 2-2h6c1.1 0 1.999.9 1.999 2H18a2 2 0 0 1 2 2v6a2 2 0 0 1-2 2h-5a2 2 0 0 1-1.997-2zm0-8v6h7v2h5.002V6H12V4z"
        />
      </svg>
    </div>

    <!-- Text Content -->
    <div class="min-w-0 flex-1">
      <h3 class="truncate font-display text-black font-stretch-semi-condensed">Link Title</h3>
      <p class="truncate text-sm text-gray-700">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit.
      </p>
    </div>

    <!-- Hover Glow Effect-->
    <div
      class="absolute inset-0 rounded-xl bg-linear-to-r from-orange-500/5 via-orange-500/36 to-orange-500/5 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
    />
  </a>
</template>
