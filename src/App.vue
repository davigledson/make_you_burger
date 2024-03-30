<script setup>
import NavBar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <main>
    <NavBar :logo="logo_src" :alt="app_name" />
    <router-view />
    <!-- exibir o conteudo da rota -->
  </main>
  <Footer />
</template>

<script>
export default {
  components: {
    NavBar,
    Footer,
  },
  data() {
    return {
      logo_src: "/img/logo.png",
      app_name: "Make your burger"
    }
  }
}

</script>

<style>
* {
  font-family: Arial, Helvetica, sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.main-container {
  margin: 50px;
  min-height: 250px;
}

h1 {
  text-align: center;
  font-size: 42px;
  margin-bottom: 20px;
  columns: #222;
}
</style>