<template>
  <header class="w-full flex flex-row items-center justify-between p-4 lg:px-20">
    <h1
      data-aos="fade-down"
      data-aos-easing="linear"
      data-aos-duration="1500"
      class="m-0 uppercase text-3xl md:text-4xl lg:text-5xl font-light"
    >
      3drobot
    </h1>

    <nav class="md:flex hidden flex-row p-4 gap-4 items-center">
      <router-link
        data-aos="fade-down"
        data-aos-easing="linear"
        data-aos-duration="1000"
        to="/"
        class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
        >Home</router-link
      >
      <router-link
        data-aos="fade-down"
        data-aos-easing="linear"
        data-aos-duration="1500"
        to="/"
        class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
        >Features</router-link
      >
      <router-link
        data-aos="fade-down"
        data-aos-easing="linear"
        data-aos-duration="2000"
        to="/"
        class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
        >Resources</router-link
      >
      <router-link
        data-aos="fade-down"
        data-aos-easing="linear"
        data-aos-duration="2500"
        to="/"
        class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
        >Docs</router-link
      >
    </nav>

    <button
      class="hidden md:block bg-[#a7a7a7] text-black py-3 px-8 rounded-full border-none font-medium transition-al duration-500 hover:bg-white cursor-pointer z-50"
    >
      Signin
    </button>
    <button @click="toggleMenu" class="cursor-pointers text-3xl p-2 z-50 md:hidden cursor-pointer">
      <i class="bx bx-menu"></i>
    </button>

    <div
      ref="mobileMenu"
      class="fixed top-16 bottom-0 left-0 right-0 mt-0 p-0 hidden md:hidden z-40 bg-black/70 backdrop-blur-md"
    >
      <nav class="flex flex-col items-center p-4 gap-6">
        <router-link
          to="/"
          class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
          >Home</router-link
        >
        <router-link
          to="/"
          class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
          >Features</router-link
        >
        <router-link
          to="/"
          class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
          >Resources</router-link
        >
        <router-link
          to="/"
          class="text-base tracking-wider transition-colors hover:text-gray-300 z-50"
          >Docs</router-link
        >
      </nav>
    </div>
  </header>
</template>

<script setup>
import 'boxicons/css/boxicons.min.css'
import { ref, onMounted } from 'vue'

const mobileMenu = ref(null)

onMounted(() => {
  console.log(mobileMenu.value)
})

const toggleMenu = () => {
  if (mobileMenu.value) {
    mobileMenu.value.classList.toggle('hidden')
  }
}
</script>
