<template>
  <div class="swiper-div">
    <div>
      <clock></clock>
    </div>
    <div>
      <swiper :options="swiperOption"  class="swiper-style">
        <swiper-slide><img src="../static/awesome-slider/space1.jpg"></swiper-slide>
        <swiper-slide><img src="../static/awesome-slider/space2.png"></swiper-slide>
        <swiper-slide><img src="../static/awesome-slider/space3.jpg"></swiper-slide>
        <swiper-slide><img src="../static/awesome-slider/space4.jpg"></swiper-slide>
        <div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
      </swiper>
    </div>
        <!--<logo/>-->
        <!--<h1 class="title">-->
          <!--NuxtApplication-->
        <!--</h1>-->
        <!--<h2 class="subtitle">-->
          <!--My stylish Nuxt.js project-->
        <!--</h2>-->
        <!--<div class="links">-->
          <!--<a-->
            <!--href="https://nuxtjs.org/"-->
            <!--target="_blank"-->
            <!--class="button&#45;&#45;green">Documentation</a>-->
          <!--<a-->
            <!--href="https://github.com/nuxt/nuxt.js"-->
            <!--target="_blank"-->
            <!--class="button&#45;&#45;grey">GitHub</a>-->
        <!--</div>-->
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
.swiper-div {
  text-align: center;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, 10%);
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
