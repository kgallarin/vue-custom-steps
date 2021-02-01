<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <stepping-sample />
    
    
  </div>
</template>

<script>
import SteppingSample from './components/SteppingSample.vue'

export default {
  name: 'App',
  components: {
    SteppingSample
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
