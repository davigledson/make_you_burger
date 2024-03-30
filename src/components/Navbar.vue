<template>
  <nav id="nav">
    <RouterLink to="/pedidos" id="logo-url">
      <img :src="logo" :alt="alt" id="logo">
    </RouterLink>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/pedidos">Pedidos</RouterLink>

  </nav>
</template>

<script>
export default {
  name: "NavBar",
  props: ['logo', 'alt']
}
</script>

<style scoped>
#nav {
  background: #222;
  border-bottom: 4px solid #222;
  padding: 15px 50px;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

 #nav #logo-url{
  margin: auto;
  margin-left: 0;

}

#logo {
  width: 40px;
  height: 40px;
}

#nav a {
  color: gold;
  margin: 12px;
  text-decoration: none;
  transition: 0.5;
}

#nav a:hover {
  color: white;
  transition: 0.5;
}
</style>