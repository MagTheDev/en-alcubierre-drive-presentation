


<template>
  <div class="h-screen w-screen bg-gradient-to-b from-deep-800 to-deep-900 flex items-center justify-center" > 
    <span class="absolute top-2 left-1/2 font-space font-semibold text-white">{{ slide }} / {{ maxSlides }} </span>
    <Intro v-if="slide === 0" class=""/>
    <Basics v-if="slide === 1" />
    <img v-if="slide === 2" src="./assets/star-trek-ship.jpg" alt="Star Trek Ship" width="1024" class="rounded">
    <Possible v-if="slide === 3"/>
    <img v-if="slide === 4" src="./assets/alcubierre.png" alt="Alcubierre Drive" width="1024" class="rounded">
  </div>
</template>

<script setup lang="ts">
import { onKeyUp } from '@vueuse/core';
import 'assets/css/tailwind.css'

const maxSlides = 4;
const slide = ref(-1);


onMounted(() => {

  onKeyUp(true, (e: KeyboardEvent) => {
    
    if (e.key === "ArrowRight") {
      nextSlide()
    } else if (e.key === "ArrowLeft") {
      prevSlide()
    }
  });

})

const nextSlide = () => {
  if (slide.value < maxSlides) {
    slide.value++
  }
}

const prevSlide = () => {
  if (slide.value > 0) {
    slide.value--
  }
}

</script>
