<script setup lang="ts">
const technologies = [
  'Python', 'SQL', 'R', 'Databricks', 'Airflow', 'Azure', 'PowerBI', 'Tableau', 'Spark'
]
</script>

<template>
  <section class="min-h-screen flex items-center justify-center bg-gradient-to-br from-primary-50 to-white dark:from-gray-900 dark:to-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-32">
      <div class="text-center">
        <div class="mx-auto mb-8 h-44 w-44 overflow-hidden rounded-full border-4 border-white shadow-xl ring-4 ring-primary-100 dark:border-gray-800 dark:ring-primary-900 sm:h-52 sm:w-52">
          <img
            src="/profile.png"
            alt="Portrait"
            class="h-full w-full object-cover object-[center_28%]"
            decoding="async"
            fetchpriority="high"
          />
        </div>
        <h1 class="text-4xl sm:text-6xl font-bold text-gray-900 dark:text-white mb-4">
          Hi, I’m Samuel. <span class="text-primary-600">👋</span>
        </h1>
        <h2 class="text-2xl sm:text-4xl font-semibold text-gray-800 dark:text-gray-100 mb-6">
          I Build Data Products That Deliver
        </h2>
        <p class="text-xl text-gray-600 dark:text-gray-300 mb-8 max-w-3xl mx-auto leading-relaxed">
          From <span class="font-semibold text-gray-900 dark:text-white">Data Engineering</span>
          and <span class="font-semibold text-gray-900 dark:text-white">Analytics</span> to
          <span class="font-semibold text-gray-900 dark:text-white"> Machine Learning</span>
          and <span class="font-semibold text-gray-900 dark:text-white">Model Deployment</span>,
          I develop end-to-end data solutions that transform raw data into trusted insights,
          intelligent products, and better business decisions.
        </p>
        <div class="flex flex-wrap justify-center gap-4 mb-12">
          <a href="#contact" class="bg-primary-600 text-white px-8 py-3 rounded-full hover:bg-primary-700 transition-colors">
            Get in Touch
          </a>
          <a href="#projects" class="border-2 border-primary-600 text-primary-600 px-8 py-3 rounded-full hover:bg-primary-50 transition-colors">
            View Projects
          </a>
        </div>
        <div class="flex flex-wrap justify-center gap-4">
          <span v-for="tech in technologies" :key="tech" class="px-4 py-2 bg-white dark:bg-gray-800 rounded-full text-sm shadow-sm">
            {{ tech }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>