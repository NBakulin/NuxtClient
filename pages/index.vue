<template>
    <div>
       <div class="swiper-button-prev" slot="button-prev"></div>
      <swiper :options="swiperOption"  class="swiper-style">
               
        <swiper-slide class="swipe-el">slide 1</swiper-slide>
        <swiper-slide class="swipe-el">slide 2</swiper-slide>
        <swiper-slide class="swipe-el">slide 3</swiper-slide>
        <swiper-slide class="swipe-el">slide 4</swiper-slide>

      
      </swiper>
        <div class="swiper-button-next" slot="button-next"></div>
      <clock></clock>
      <!-- <logo/> -->
      <!-- <h1 class="title">
        NuxtApplication
      </h1>
      <h2 class="subtitle">
        My stylish Nuxt.js project
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green">Documentation</a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey">GitHub</a>
      </div> -->
    </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import clock from '~/components/clock.vue'

export default {
  components: {
    Logo,
    swiper,
    swiperSlide,
    clock
  },
  data() {
    return {
      swiperOption: {
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      }
    }
  }
}
</script>

<style>
body {
  background-color: black;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.swiper-slide img {
  width: 100%;
  color: white;
}

.swipe-el {
  color: white;
  font-size: 2em;
}

.swiper-style {
  width: 900px;
  align-items: center;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
