<template>
  <div id="app">
     <pokedex />
  </div>
</template>

<script>
import Pokedex from './components/Pokedex.vue'

export default {
  
  components: {
    Pokedex
  }
}
</script>

<style lang="scss">
  @import url('https://use.fontawesome.com/releases/v5.8.2/css/all.css');
  body {
    margin: 0;
    padding: 0;
  }
</style>
