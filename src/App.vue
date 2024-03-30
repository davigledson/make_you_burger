<script setup>
import NavBar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <main>
    <NavBar />
    <router-view/>  
    <!-- exibir o conteudo da rota -->
  </main>
  <Footer/>
</template>

<script>
export default {
  components: {
  NavBar,
  Footer,
}
}

</script>