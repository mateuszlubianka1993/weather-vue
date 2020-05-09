<template>
  <div id="app">
    <SearchBar @dataFetched="getWeatherData" />
    <CurrentDay :weather="weather" :exist="exist" />
    <Footer :days="nextDays" :exist="exist" />
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
      exist: false,
      daysOfWeek: ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"],
      nextDays: []
    }
  },
  methods: {
    getWeatherData(data) {
      // console.log(data)
      this.weather = data;
      this.exist = true;

      let days = [];
      let number = new Date().getDay();

      for(let i=1; i<=4; i++) {
        number++;
        if(number >= 7) {
          number = 0;
        }

        days.push({
          name: this.daysOfWeek[number],
          data: this.weather.list[i*8]
        })
      }
      this.nextDays = days;
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
