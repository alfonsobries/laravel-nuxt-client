<template>
  <div>
    <div class="text-center">
      <div class="font-semibold text-6xl text-gray-900">
        {{ title }}
      </div>

      <div class="flex justify-between">
        <a 
          class="text-gray-800 uppercase" 
          href="https://tailwindcss.com/">TailwindCSS</a>
        <a 
          class="text-gray-800 uppercase" 
          href="https://laravel.com/">Laravel.com</a>
        <a 
          class="text-gray-800 uppercase" 
          href="https://vuejs.org/">VueJs</a>
        <a 
          class="text-gray-800 uppercase" 
          href="https://nuxtjs.org/">Nuxtjs</a>
        <a 
          class="text-gray-800 uppercase" 
          href="https://vue-tailwind.com/">Vue Tailwind</a>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  head () {
    return { title: this.$t('home') }
  },

  data: () => ({
    title: process.env.appName
  }),

  computed: mapGetters({
    authenticated: 'auth/check'
  })
}
</script>
