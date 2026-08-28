<script setup lang="ts">
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const message = ref('')

const sendMessage = () => {
  const subject = `Portfolio contact from ${name.value}`
  const body = `Name: ${name.value}\nEmail: ${email.value}\nMessage: ${message.value}`

  window.location.href = `mailto:adurojasamuel@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`
}
</script>

<template>
  <section id="contact" class="py-20 bg-gray-50 dark:bg-gray-900">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="section-title">Get in Touch</h2>
      <div class="max-w-2xl mx-auto">
        <form class="space-y-6" @submit.prevent="sendMessage">
          <div>
            <label for="name" class="block text-sm font-medium mb-2">Name</label>
            <input v-model="name" type="text" id="name" name="name" required
              class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 focus:ring-2 focus:ring-primary-500 focus:border-transparent">
          </div>
          <div>
            <label for="email" class="block text-sm font-medium mb-2">Email</label>
            <input v-model="email" type="email" id="email" name="email" required
              class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 focus:ring-2 focus:ring-primary-500 focus:border-transparent">
          </div>
          <div>
            <label for="message" class="block text-sm font-medium mb-2">Message</label>
            <textarea v-model="message" id="message" name="message" rows="4" required
              class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 focus:ring-2 focus:ring-primary-500 focus:border-transparent"></textarea>
          </div>
          <button type="submit"
            class="w-full bg-primary-600 text-white py-3 px-6 rounded-lg hover:bg-primary-700 transition-colors">
            Send Message
          </button>
        </form>
      </div>
    </div>
  </section>
</template>