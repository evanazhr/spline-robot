<template>
  <div
    class="flex lg:mt-20 flex-col lg:flex-row items-center justify-between min-h-[calc(90vh-6rem)]"
  >
    <div
      data-aos="fade-right"
      data-aos-offset="300"
      data-aos-easing="ease-in-sine"
      class="max-w-xl ml-[5%] z-10 mt-[90%] md:mt-[60%] lg:mt-0"
    >
      <div
        class="relative w-[95%] sm:w-48 h-10 bg-gradient-to-r from-[#656565] to-[#e99b63] shadow-[0_0_15px_rgba(255,255,0.4)] rounded-full"
      >
        <div
          class="inset-[3px] absolute bg-black rounded-full flex items-center justify-center gap-1"
        >
          <i class="bx bx-diamond"></i>
          INTRODUCING
        </div>
      </div>
      <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-semibold tracking-wider my-8">
        Email For <br />
        Developers
      </h1>
      <p class="text-base sm:text-lg tracking-wider text-gray-400 max-w-[25rem] lg:max-w-[30rem]">
        the best way to reach humans instead of spam folders, deliver transactional and marketing
        emails at scale
      </p>

      <div class="flex gap-4 mt-12">
        <a
          href="#"
          class="border border-[#2a2a2a] px-2 py-2 sm:py-3 sm:px-5 rounded-full sm:text-lg text-sm font-semibold tracking-wider transition-all duration-300 bg-[#1a1a1a] hover:bg-gray-300 hover:text-black text-white"
        >
          Documentation
          <i class="bx bx-link-external"></i>
        </a>
        <a
          href="#"
          class="border border-[#2a2a2a] px-2 py-2 sm:py-3 sm:px-5 rounded-full sm:text-lg text-sm font-semibold tracking-wider transition-all duration-300 hover:bg-[#1a1a1a] bg-gray-300 text-black hover:text-white"
        >
          Get Started
          <i class="bx bx-link-external"></i>
        </a>
      </div>
      <canvas
        data-aos="fade-zoom-in"
        data-aos-easing="ease-in-back"
        data-aos-delay="300"
        data-aos-offset="0"
        data-aos-duration="3000"
        class="absolute -z-10 lg:top-0 top-[-20%] bottom-0 lg:left-[25%] sm:left-[-20%] h-full"
        ref="canvas"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, reactive, onMounted } from 'vue'
import { Application } from '@splinetool/runtime'
import AOS from 'aos'
import 'aos/dist/aos.css'

// template ref
const canvas = ref(null)

// spline state
const state = reactive({
  spline: {
    scene: 'https://prod.spline.design/sJOJapO8Ig4XHfqX/scene.splinecode',
    app: null,
    isLoaded: false,
  },
})

onMounted(async () => {
  const app = new Application(canvas.value)
  await app.load(state.spline.scene)
  state.spline.app = app
  state.spline.isLoaded = true
  AOS.init({
    duration: 1500,
    once: true,
  })
})
</script>
