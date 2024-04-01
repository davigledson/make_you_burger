<template>
  <div class="main-container">
    <h1>Gerenciar PEDIDOS</h1>
    <Dashboard/>
  </div>
</template>

<script>
import Dashboard from '../components/DashBoard.vue'
export default {
  name:"Pedidos",
  components: {
    Dashboard
  }
}


</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
