<template>
  <div id="app">
    <SearchBar/>
    <CurrentDay/>
    <Footer/>
  </div>
</template>

<script>
import CurrentDay from './components/CurrentDay';
import SearchBar from './components/SearchBar';
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    CurrentDay,
    SearchBar,
    Footer
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
}
</style>
