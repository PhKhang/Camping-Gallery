<script setup>
import { RouterLink, RouterView } from 'vue-router'
import {Cloudinary} from "@cloudinary/url-gen";
import HelloWorld from './components/HelloWorld.vue'
import { AdvancedImage } from "@cloudinary/vue";
import { fill } from "@cloudinary/url-gen/actions/resize";

const cld = new Cloudinary({cloud: {cloudName: 'dwgvuiqq6',},});
const fonts = import.meta.glob('@/assets/*.jpg')
// for len(fonts){
//   console.log(fonts)
// }
</script>

<template>
  <div class="main">
    
    <header>
      <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->
      <div class="">
        <!-- <HelloWorld msg="You did it!" /> -->
        <!-- <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
        </nav> -->
      </div>
    </header>
    
    <h1>Xin chào từ Đội Sói</h1>
    <h2>Những kỷ niệm nơi đất trại...</h2>
    <div class="gall">
      <img src="@/assets/firstDay.jpg" alt="" srcset="">
      <img src="@/assets/buildThing.jpg" alt="" srcset="">
      <img src="@/assets/discuss.jpg" alt="" srcset="">
      <img src="@/assets/learn2.jpg" alt="" srcset="">
      <img src="@/assets/truc.jpg" alt="" srcset="">
      <img src="@/assets/truc1.jpg" alt="" srcset="">
    </div>
    
    <h2>Mini game</h2>
    <img src="@/Minigame-tìm-từ (1)1.jpg" alt="" srcset="">
    <!-- <img :src="url" alt="" srcset=""> -->
    <!-- <RouterView /> -->
    
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.main {
  width: 100%;
  max-width: 1000px;
  padding: auto;
}

.gall {
  width: 100%;
  background-color: darkslategray;
  display: flex;
  flex-direction: column;
}

img {
  border-radius: 10px;
  margin: 10px;
  max-width: 500px;
  object-fit: cover;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
