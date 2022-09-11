<template>
  <div id="about">

    <div class="main-content">
      <h1>Sobre mim...</h1>
      <p>
        Meu nome é Marcos, tenho 27 anos e sou formado em
        <b>Análise e Desenvolvimento de Sistemas</b> pela Uninter, atualmente
        trabalho com desenvolvimento web fullstack, sendo focado em <b>PHP</b> e
        <b>JavaScript</b>.
      </p>
      <p>
        Tenho grande interesse em tecnologias FrontEnd e no momento venho me
        desenvolvendo em <b>VueJS</b>, e para o backend venho estudando o
        framework <b>Laravel</b>.
      </p>
      <p>Aqui voce tem acesso ao meu curriculo.</p>
      <button class="btn">
        <a href="./">Download CV</a>
      </button>
    </div>

    <div class="main-content">
      <h3>Algumas das minhas skills</h3>
      <div class="icons-services">
        <img src="../assets/html.png" class="icon-img">
        <img src="../assets/css.png" class="icon-img">
        <img src="../assets/js.png" class="icon-img">
        <img src="../assets/php.png" class="icon-img">
        <img src="../assets/git.png" class="icon-img">
        <img src="../assets/mysql.png" class="icon-img">
        <img src="../assets/docker.png" class="icon-img">
        <img src="../assets/vue.png" class="icon-img">
        <img src="../assets/react.png" class="icon-img">
        <img src="../assets/sass.png" class="icon-img">

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AbouView",
  components: {},
};
</script>

<style scoped>
#about {
  display: flex;
  max-width: 110rem;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.icons-services {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
}

.main-content {
  color: #fff;
  display: flex;
  align-items: left;
  flex-direction: column;
  margin: 0 auto;
  padding: 7rem;
}

.main-content h1 {
  font-size: 2.5rem;
}

.main-content p {
  font-size: 1.2rem;
  width: 80%;
}

.icons-services .icon-img {
  width: 2.6rem;
  height: 2.2rem;
  margin-top: 10px;
}

.btn {
  background-color: #fbeee0;
  border: 2px solid #0a0702;
  width: 12rem;
  margin-top: 1rem;
  border-radius: 10px;
  box-shadow: #030200 4px 4px 0 0;
  color: #0e0a05;
  cursor: pointer;
  display: inline-block;
  font-weight: 600;
  font-size: 18px;
  padding: 0 18px;
  line-height: 50px;
  text-align: center;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.btn:hover {
  background-color: #fff;
}

.btn:active {
  box-shadow: #050301 2px 2px 0 0;
  transform: translate(2px, 2px);
}

@media (max-width: 768px) {
  .main-content {
    padding: 5rem;
  }

  .main-content h1 {
    font-size: 3rem;
  }

  .main-content p {
    font-size: 1.3rem;
    width: 100%;
  }

  .btn {
    min-width: 120px;
    padding: 0 25px;
  }
}
</style>
