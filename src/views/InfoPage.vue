<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Lucio Peraza',
  avatar: 'https://api.dicebear.com/9.x/big-ears-neutral/svg?seed=Lucio',
  about: 'I am a passionate full stack developer with experience building modern web applications',
  skills: ['Python', 'C++', 'C#', 'Vue.js', 'Node.js', 'Tailwind CSS'],
  email: 'lperaza2@example.com',
  location: 'Hidalgo, Texas',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="my-8 self-start text-sm text-black underline-offset-4 transition-colors duration-200 hover:text-red-600 hover:underline"
    >
      ← Back to Links
    </RouterLink>

    <!-- Profile Card -->
    <div
      class="w-full max-w-lg rounded-2xl border border-orange-500 bg-yellow-600 p-6 shadow-xl shadow-orange-400/50 sm:p-8"
    >
      <!-- Header -->
      <div class="mb-6 flex flex-col items-center text-center sm:flex-row sm:text-left">
        <div
          class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-yellow-400 sm:mr-6 sm:mb-6"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-amber-200">{{ bio.name }}</h1>
          <p class="text-small text-amber-100">📍 {{ bio.location }}</p>
        </div>
      </div>

      <!-- About Section -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg text-amber-200 font-stretch-semi-condensed">About</h2>
        <p class="leading-relaxed text-amber-50">{{ bio.about }}</p>
      </div>

      <!-- Skill Section -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg text-amber-200 font-stretch-semi-condensed">Skills</h2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full bg-yellow-900/50 px-3 py-1 text-sm text-amber-200"
            >{{ skill }}
          </span>
        </div>
      </div>
      <!-- Contact -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg text-amber-200 font-stretch-semi-condensed">Get In Touch</h2>
        <a
          :href="`mailto:${bio.email}`"
          class="group inline-flex items-center gap-2 rounded-xl bg-yellow-500 px-6 py-3 font-medium text-amber-100 shadow-lg shadow-orange-400/30 transition-all duration-200 hover:scale-105 hover:bg-yellow-700 hover:shadow-xl hover:shadow-orange-500 active:scale-95"
        >
          <svg
            data-slot="icon"
            aria-hidden="true"
            fill="none"
            stroke-width="1.5"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12"
          >
            <path
              d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </svg>
          Send Email
        </a>
      </div>
    </div>
  </main>
</template>
