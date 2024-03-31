

<template>
  <Banner/>
  
  <p>banner</p>
  <main class="main-container">
 <h1>Monte o seu burger</h1>
 <BurguerForm/>
 <p>formulario</p>
  </main>
</template>

<script>
import Banner from "../components/Banner.vue"
import BurguerForm from "../components/BurguerForm.vue"

export default {
  name: "Home",
  components: {
    Banner,
    BurguerForm
  }
}
</script>