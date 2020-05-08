<template>
  <div id="app">
    <SearchBar @dataFetched="getWeatherData" />
    <CurrentDay :weather="weather" :exist="exist" />
    <Footer/>
  </div>
</template>

<script>
import CurrentDay from './components/CurrentDay';
import SearchBar from './components/SearchBar';
import Footer from './components/Footer';

export default {
  name: 'App',
  data: function() {
    return {
      weather: {},
      exist: false
    }
  },
  methods: {
    getWeatherData(data) {
      console.log(data)
      this.weather = data;
      this.exist = true;
    }
  },
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
