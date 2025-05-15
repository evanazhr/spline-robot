<!-- src/views/HomeView.vue -->
<template>
  <img
    src="@/assets/img/gradient.png"
    alt="gradient"
    class="opacity-60 absolute top-[5%] w-xl right-[5%] -z-50"
  />
  <div
    class="w-xl h-0 shadow-[0_0_900px_20px_#e99b63] -rotate-45 absolute top-[10%] -right-[5%]"
  ></div>
  <Hero />
</template>

<script setup>
import Hero from '@/components/Hero.vue'
import AOS from 'aos'
import 'aos/dist/aos.css' // You can also use <link> for styles
// ..
AOS.init()
</script>
