<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>
    {{nametable}}
  </h1>
  <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <hr>
  <index/>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Index from './components/Index.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    Index
  },
  data(){
    return{
    nametable: "Lista de tareas VueJs"
    }
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
