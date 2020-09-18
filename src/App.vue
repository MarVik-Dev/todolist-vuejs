<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <header-top></header-top>
    <mon-contenu></mon-contenu>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Header from "./components/Header"
import Contenu from "./components/Contenu"

export default {
  name: 'App',
  components: {
    // HelloWorld,
    'header-top': Header,
    'mon-contenu': Contenu
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
