<template>

  <!-- <main-header :navItems="navItems" /> -->
  <!-- <router-view v-slot="{ Component }">
    <transition name="slide">
      <component :is="Component" />
    </transition>
  </router-view> -->
  <main-container>
    <home-view></home-view>
  </main-container>
  <main-container>
    <about-view></about-view>
  </main-container>

  <main-container>
    <portfolio-view></portfolio-view>
  </main-container>
</template>

<script>
import MainHeader from "@/components/MainHeader.vue";
import MainContainer from "@/components/MainContainer.vue";
import HomeView from "./views/HomeView.vue";
import AboutView from "./views/AboutView.vue";
import PortfolioView from "./views/PortfolioView.vue";

import { reactive } from "vue";
export default {
  components: {
    MainHeader,
    MainContainer,
    HomeView,
    AboutView,
    PortfolioView
  },
  setup() {
    const navItems = reactive([
      {
        id: 1,
        name: "Home",
        path: "/",
      },
      {
        id: 2,
        name: "Sobre",
        path: "/about",
      },
      {
        id: 3,
        name: "Portfolio",
        path: "/portfolio",
      },
    ]);

    return {
      navItems,
    };
  },
};
</script>

<style>
/*
font-family: 'Lobster', cursive;
font-family: 'Poppins', sans-serif;
*/
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 62, 5%;
  font-family: "Poppins", sans-serif;
  color: #fff;
  /* overflow: hidden; */
}

body {
  width: 100vw;
  background: url("./assets/bg.jpg") no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  backdrop-filter: brightness(50%);
}

/* body {
  background: linear-gradient(0, #120c56, #000000);
} */


a {
  text-decoration: none;
}

ul,
li {
  list-style: none;
}


.container-stars {
  background-size: cover;
  width: 100px;
}
</style>
