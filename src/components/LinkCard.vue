<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  url: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    default: '',
  },
  icon: {
    type: String,
    default: 'flag',
  },
})

const icons = {
  flag: `        <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 12v9a1 1 0 0 1-2 0V4c0-1.1.9-2 2-2h6c1.1 0 1.999.9 1.999 2H18a2 2 0 0 1 2 2v6a2 2 0 0 1-2 2h-5a2 2 0 0 1-1.997-2zm0-8v6h7v2h5.002V6H12V4z"
          />`,
  code: `<path d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5" stroke-width="2"stroke-linecap="round" stroke-linejoin="round"></path>`,
  briefcase: `<path d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 0 0 .75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 0 0-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0 1 12 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 0 1-.673-.38m0 0A2.18 2.18 0 0 1 3 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 0 1 3.413-.387m7.5 0V5.25A2.25 2.25 0 0 0 13.5 3h-3a2.25 2.25 0 0 0-2.25 2.25v.894m7.5 0a48.667 48.667 0 0 0-7.5 0M12 12.75h.008v.008H12v-.008Z" stroke-linecap="round" stroke-width="2" stroke-linejoin="round"></path>
  </svg>`,
  money: ` <path d="M2.25 18.75a60.07 60.07 0 0 1 15.797 2.101c.727.198 1.453-.342 1.453-1.096V18.75M3.75 4.5v.75A.75.75 0 0 1 3 6h-.75m0 0v-.375c0-.621.504-1.125 1.125-1.125H20.25M2.25 6v9m18-10.5v.75c0 .414.336.75.75.75h.75m-1.5-1.5h.375c.621 0 1.125.504 1.125 1.125v9.75c0 .621-.504 1.125-1.125 1.125h-.375m1.5-1.5H21a.75.75 0 0 0-.75.75v.75m0 0H3.75m0 0h-.375a1.125 1.125 0 0 1-1.125-1.125V15m1.5 1.5v-.75A.75.75 0 0 0 3 15h-.75M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Zm3 0h.008v.008H18V10.5Zm-12 0h.008v.008H6V10.5Z" stroke-linecap="round" stroke-width="2" stroke-linejoin="round"></path>`,
  roll: `<svg xmlns="http://www.w3.org/2000/svg" width="33" height="33" viewBox="65 65 512 512"><!-- Icon from Game Icons by GameIcons - https://github.com/game-icons/icons/blob/master/license.txt --><path fill="currentColor" d="M255.76 44.764c-6.176 0-12.353 1.384-17.137 4.152L85.87 137.276c-9.57 5.536-9.57 14.29 0 19.826l152.753 88.36c9.57 5.536 24.703 5.536 34.272 0l152.753-88.36c9.57-5.535 9.57-14.29 0-19.825l-152.753-88.36c-4.785-2.77-10.96-4.153-17.135-4.153m-.824 53.11q13.52.146 24.31 6.192q7.38 4.136 9.666 9.438q2.21 5.261.26 13.865l-1.6 5.706q-1.59 6.125-.66 8.81q.854 2.645 4.242 4.544l3.39 1.898l-33.235 18.62l-3.693-2.067q-6.176-3.459-7.883-7.82q-1.782-4.402.594-14.005l1.524-5.748q1.33-5.135.26-8.418q-.98-3.336-4.444-5.277q-5.273-2.954-12.63-2.123q-7.433.79-15.35 5.225q-7.457 4.178-13.55 10.46q-6.167 6.243-10.587 14.288L171.9 138.21q7.977-8.01 15.676-14.013q7.7-6 16.262-10.8q22.464-12.586 41.78-14.967a69 69 0 0 1 9.32-.557zm50.757 56.7l26.815 15.024l-33.235 18.62l-26.816-15.023l33.236-18.62zM75.67 173.84c-5.753-.155-9.664 4.336-9.664 12.28v157.696c0 11.052 7.57 24.163 17.14 29.69l146.93 84.848c9.57 5.526 17.14 1.156 17.14-9.895V290.76c0-11.052-7.57-24.16-17.14-29.688l-146.93-84.847c-2.69-1.555-5.225-2.327-7.476-2.387zm360.773.002c-2.25.06-4.783.83-7.474 2.385l-146.935 84.847c-9.57 5.527-17.14 18.638-17.14 29.69v157.7c0 11.05 7.57 15.418 17.14 9.89L428.97 373.51c9.57-5.527 17.137-18.636 17.137-29.688v-157.7c0-7.942-3.91-12.432-9.664-12.278zm-321.545 63.752q9.83 2.05 17.954 5.013a99.6 99.6 0 0 1 15.68 7.325q19.82 11.445 30.218 26.082q10.398 14.55 10.398 31.04q0 8.46-3.168 13.364q-3.169 4.818-10.804 8.094l-5.2 1.92q-5.524 2.163-7.23 4.46q-1.705 2.207-1.705 6.092v3.885l-29.325-16.933v-4.23q-.001-7.08 2.68-10.97q2.681-3.977 11.292-7.467l5.2-2.006q4.63-1.815 6.742-4.567q2.191-2.704 2.192-6.676q0-6.041-3.9-11.66q-3.899-5.705-10.885-9.74q-6.58-3.798-14.217-5.272q-7.636-1.56-15.922-.645v-27.11zm269.54 8.607q2.282 0 4.232.493q10.398 2.543 10.398 19.034q0 8.46-3.168 17.023q-3.168 8.476-10.804 20.568l-5.2 7.924q-5.524 8.542-7.23 12.807q-1.705 4.178-1.705 8.063v3.885l-29.325 16.932v-4.23q0-7.08 2.68-14.067q2.683-7.073 11.292-20.504l5.2-8.01q4.63-7.164 6.742-12.354q2.191-5.238 2.192-9.21q0-6.042-3.898-7.158q-3.9-1.201-10.887 2.83q-6.58 3.801-14.215 11.145q-7.635 7.259-15.922 17.74v-27.11q9.83-9.3 17.95-15.718q8.126-6.417 15.68-10.777q16.106-9.3 25.99-9.307zm-252.723 94.515l29.326 16.93v30.736l-29.325-16.93v-30.735zm239.246 8.06v30.735l-29.325 16.93v-30.733l29.326-16.932z"/></svg>`,
}
</script>

<template>
  <a
    :href="url"
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
        v-html="icons[icon] || icons.flag"
      ></svg>
    </div>

    <!-- Text Content -->
    <div class="min-w-0 flex-1">
      <h3 class="truncate font-display text-black font-stretch-semi-condensed">{{ title }}</h3>
      <p class="truncate text-sm text-gray-700">
        {{ description }}
      </p>
    </div>

    <!-- Hover Glow Effect-->
    <div
      class="absolute inset-0 rounded-xl bg-linear-to-r from-orange-500/5 via-orange-500/36 to-orange-500/5 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
    />
  </a>
</template>
