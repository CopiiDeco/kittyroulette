<template>
  <div id="app">
    <KittyRoulette msg="This is the best cat roulette of the interwebz"/>
  </div>
</template>

<script>
import KittyRoulette from './components/KittyRoulette.vue'

export default {
  name: 'App',
  components: {
    KittyRoulette
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
