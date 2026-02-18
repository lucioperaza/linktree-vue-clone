<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

const profile = ref({
  name: 'Lucio Peraza',
  slogan: 'Full Stack Developer and Student',
  avatar: 'https://api.dicebear.com/9.x/big-ears-neutral/svg?seed=Lucio',
  links: [
    {
      id: 1,
      title: 'Github',
      url: 'https://github.com/lucioperaza',
      icon: 'code',
      description: 'Check out my projects',
    },
    {
      id: 2,
      title: 'Linkedin',
      url: 'https://www.linkedin.com/in/lucio-peraza-168b9587',
      icon: 'briefcase',
      description: 'Connect with me professionally',
    },
    {
      id: 3,
      title: 'Expense Splitter',
      url: 'https://expense-splitter-vue.lucio-peraza54.workers.dev/',
      icon: 'money',
      description: 'Check out my expense splitter project',
    },
  ],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header-->
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-yellow-600 shadow-lg shadow-orange-500/20 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-black sm:text-3xl">
        {{ profile.name }}
      </h1>
      <p class="max-w-xs text-gray-800 sm:text-lg">{{ profile.slogan }}</p>
    </div>

    <!--Link Card-->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!--Navigate to Info-->
    <RouterLink
      to="/info"
      class="mt-8 text-sm text-black underline-offset-4 transition-colors duration-200 hover:text-yellow-600 hover:underline"
      >About Me →</RouterLink
    >
  </main>
</template>
