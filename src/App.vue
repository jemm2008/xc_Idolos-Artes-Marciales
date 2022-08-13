<template>
  <div id="app">
    <div id="nav">
      <img alt="logo" src="./assets/img/logo.jpg"><br><br>
      <router-link class="text-white" :to="{ name: 'home' }">Home</router-link> |
      <router-link :to="{ name: 'list' }">Lista de peleadores</router-link> |
      <router-link :to="{ name: 'search' }">Buscador</router-link>
    </div>
    <router-view />
  </div>

</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
body {
  background-image: url("./assets/img/bg.png");
  background-color: cadetblue;
  height: 100vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: white;
}

#nav a.router-link-exact-active {
  color: #c42741;
}
</style>
