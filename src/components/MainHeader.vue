<template>
  <nav>
    <ul class="nav-list">
      <router-link
        class="nav-item"
        v-for="nav in navItems"
        :key="nav.id"
        :to="nav.path"
      >
        {{ nav.name }}
      </router-link>
    </ul>
  </nav>
</template>
<script>
// import { ref } from "vue";
export default {
  props: ["navItems"],
  setup() {
    return {};
  },
};
</script>
<style  scoped>
nav {
  position: fixed;
  width: 100%;
  height: auto;
}
nav .nav-list {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  position: relative;
}

.nav-list .nav-item {
  font-size: 1.6rem;
  font-family: "Lobster", cursive;
  color: #fff;
  transition: 0.3s all;
}

.nav-list a::after {
  content: "";
  display: flex;
  width: 0%;
  height: 0.125rem;
  background: rgb(158, 156, 156);
  margin: 0.5rem auto;
  transition: width 0.3s;
}

.nav-list a:hover {
  color: rgb(158, 156, 156);
}

.nav-list a:hover::after {
  width: 100%;
}
</style>