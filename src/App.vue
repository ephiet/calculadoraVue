<template>
  <div id="app">
    
    <calculadora msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import calculadora from './components/calculadora.vue'

export default {
  name: 'App',
  components: {
    calculadora
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  height:100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
body{
  margin:0;
  padding:0;
  height:100%;
  display: flex;
  justify-content: center;
  align-items: center;
  
}
</style>
