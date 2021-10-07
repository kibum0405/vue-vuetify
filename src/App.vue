<template>
  <div id="app">
    <GetStarted msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import GetStarted from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    GetStarted
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
