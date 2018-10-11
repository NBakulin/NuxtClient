<template>
  <div class="swiper-div">
    <div class="bootstrap-navbar-div">
      <b-navbar 
        toggleable="md" 
        type="dark"
        variant="dark">
        <b-navbar-toggle target="nav_collapse"/>

        <b-navbar-brand href="#">NavBar</b-navbar-brand>

        <b-collapse 
          id="nav_collapse" 
          is-nav>

          <b-navbar-nav>
            <b-nav-item href="#">Link</b-nav-item>
            <b-nav-item 
              href="#" 
              disabled>Disabled</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">

            <b-nav-form>
              <b-form-input 
                size="sm" 
                class="mr-sm-2" 
                type="text" 
                placeholder="Search"/>
              <b-button 
                size="sm" 
                class="my-2 my-sm-0" 
                type="submit">Search</b-button>
            </b-nav-form>

            <b-nav-item-dropdown 
              text="Lang" 
              right>
              <b-dropdown-item href="#">EN</b-dropdown-item>
              <b-dropdown-item href="#">ES</b-dropdown-item>
              <b-dropdown-item href="#">RU</b-dropdown-item>
              <b-dropdown-item href="#">FA</b-dropdown-item>
            </b-nav-item-dropdown>

            <b-nav-item-dropdown right>
              <!-- Using button-content slot -->
              <template slot="button-content">
                <em>User</em>
              </template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Signout</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>

        </b-collapse>
      </b-navbar>
    </div>
    <div>
      <clock/>
    </div>
    <div>
      <swiper 
        :options="swiperOption" 
        class="swiper-style">
        <swiper-slide><img src="../static/awesome-slider/space1.jpg"></swiper-slide>
        <swiper-slide><img src="../static/awesome-slider/space2.png"></swiper-slide>
        <swiper-slide><img src="../static/awesome-slider/space3.jpg"></swiper-slide>
        <swiper-slide><img src="../static/awesome-slider/space4.jpg"></swiper-slide>
        <div 
          slot="button-prev" 
          class="swiper-button-prev"/>
        <div 
          slot="button-next" 
          class="swiper-button-next"/>
      </swiper>
    </div>
    <div>
      <textarea 
        rows="4" 
        cols="50"
        class="textArea"
        disabled>
        Cosmos is great, really!
      </textarea>
    </div>
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
  background: radial-gradient(ellipse at center, #0a2e38 0%, #000000 70%);
  background-size: 100%;
}
.swiper-div {
  text-align: center;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, 10%);
}
.bootstrap-navbar-div {
  text-align: center;
  position: relative;
  /*left: 50%;*/
  /*top: 50%;*/
  transform: translate(0%, -160%);
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

.textArea {
  transform: translate(0, 10%);
  dismin-height: 100%;
  min-width: 100%;
  border: transparent;
  font-family: 'Share Tech Mono', monospace;
  color: #ffffff;
  text-align: center;
  position: relative;
  font-size: 22px;
  color: #daf6ff;
  text-shadow: 0 0 20px rgba(10, 175, 230, 1), 0 0 20px rgba(10, 175, 230, 0);
  background: #0f3854;
  background: radial-gradient(ellipse at center, #0a2e38 0%, #000000 70%);
  background-size: 100%;
}

.links {
  padding-top: 15px;
}
</style>
