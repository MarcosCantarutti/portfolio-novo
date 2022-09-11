<template>
  <div class="main-content">
    <div class="title-container">
      <h1>Meus projetos</h1>
      <i class="bi bi-archive"></i>
    </div>
    <div class="container">
      <div class="card" v-for="link in links" :key="link.id" v-show="link.visibility == 'public'">
        <h3 class="title">{{ link.name }}</h3>
        <div class="description-container">
          <span>{{ link.description }}</span>
        </div>
        <div class="link-container">
          <a :href="link.html_url" target="_blank">Clique aqui e confira!</a>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import { ref } from "vue";
import { onMounted } from "@vue/runtime-core";
export default {
  name: "PortfolioView",
  components: {},

  setup() {
    const url = "https://api.github.com/users/MarcosCantarutti/repos";

    let links = ref({});

    const getLinks = () => {
      fetch(url).then((Response) => {
        Response.json().then((data) => (links.value = data));
      });
    };

    onMounted(() => {
      getLinks();
      console.log(links);
    });

    return {
      url,
      links,
    };
  },
};
</script>

<style scoped>
.main-content {
  margin: 0 auto;
  /* width: 800px; */
}

.title-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 10px;
  margin-bottom: 30px;
}

.title-container .bi {
  color: #fff;
  font-size: 2rem;
}

.main-content .title-container h1 {
  text-align: center;
  color: #fff;
  font-weight: 600;
}

.container {
  height: 500px;
  width: 100%;
  display: flex;
}


.card {
  display: flex;
  height: 320px;
  width: 500px;
  background: rgb(8, 21, 38);
  background: linear-gradient(0deg, rgba(8, 21, 38, 1) 0%, rgba(8, 42, 77, 1) 100%);
  border-radius: 10px;
  border: 2px solid;
  /* background-color: #17141d; */
  /* box-shadow: -1rem 0 3rem #000; */
  /* margin-left: -200px; */
  transition: 0.4s ease-out;
  position: relative;
  left: 0px;
  cursor: pointer;
}

.card:not(:first-child) {
  margin-left: -225px;
}

.card:hover {
  transform: translateY(-225px);
  transition: 1s ease-out;
}

.card:hover~.card {
  position: relative;
  left: 150px;
  transition: 1s ease-out;
}

.title {
  color: #fff;
  font-weight: 300;
  font-size: 1rem;
  /* position: absolute; */
  /* left: 50px;
  top: 15px; */
  margin: 10px auto 0;
}

.description-container {
  text-align: center;
  margin-top: 10px;
  color: #fff;
  font-weight: 300;
  padding: 36px;
  font-size: 1rem;
}

.link-container {
  text-align: center;
  font-size: 1rem;
  margin-bottom: 10px;
  font-weight: 300;
}
</style>
