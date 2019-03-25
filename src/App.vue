<template>
  <div id="app">
    <img id="logo" alt="Logo" src="http://www.albertomrodriguez.com/wp-content/uploads/2017/06/cropped-logo-letra.png"/>
    <Inicio/>
  </div>
</template>

<script>
import Inicio from './components/Inicio.vue'

export default {
  name: 'app',
  components: {
    Inicio
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
#logo {
  width: 15%;
  height: 20%;
}
</style>
