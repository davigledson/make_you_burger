

<template>
  <Banner/>
  
 
  <main class="main-container">
 <h1>Monte o seu burger</h1>
 <BurguerForm/>
 
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