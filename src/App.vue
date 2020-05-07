<template>
  <div id="app">
    <CurrentDay/>
  </div>
</template>

<script>
import CurrentDay from './components/CurrentDay';

export default {
  name: 'App',
  components: {
    CurrentDay
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
