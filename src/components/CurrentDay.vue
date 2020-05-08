<template>
  <div class="current-day d-flex align-items-center" v-bind:class = "(timeOfDay === 'day') ? 'day' : 'night'">
    <div class="weather-container container" v-if="exist">
      <div class="weather-icon text-center">
        <i v-if="timeOfDay === 'day'" class="fas fa-cloud-sun"></i>  <i v-else class="fas fa-cloud-moon"></i>
      </div>
      <div class="weather-data container">
        <div class="row">
          <div class="data-box temperature">
            {{Math.round(weather.list[0].main.temp)}}&ordm;C
          </div>
          <div class="data-box d-flex flex-column justify-content-between">
            <div class="wind text-justify">{{weather.list[0].wind.speed}}km/h</div>
            <div class="humidity text-justify">{{weather.list[0].main.humidity}}%</div>
          </div>
          <div class="data-box description d-flex align-items-end">
            <span>{{weather.list[0].weather[0].main}}</span>
          </div>
        </div>
      </div>
      <div class="location-data container text-justify">
        <div class="location-box">
          <i class="fas fa-map-marker-alt"></i> {{weather.city.name}}
        </div>
        <div class="location-box d-flex justify-content-between">
          <div class="date">
            {{new Date().toDateString()}}
          </div>
          <div class="time">
            {{new Date().getHours()}}:{{new Date().getMinutes()}}
          </div>
        </div>
      </div>
    </div>
    <div class="weather-container container" v-else>
      <h2>Hello!</h2>
      <h3>Search weather data by city name.</h3>
      <h2><i class="fas fa-search"></i></h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CurrentDay',
  props: ['weather', 'exist'],
  data: function() {
    return {
      timeOfDay: 'day'
    }
  },
  methods: {
    dayOrNight() {
      const time = new Date().getHours();
      // const time = 23;

      if(time >= 18 || time < 5) {

        this.timeOfDay = 'night'
      } else {

        this.timeOfDay = 'day'
      }
    }
  },
  created: function () {
    this.dayOrNight();
  }
}
</script>

<style scoped>
  .weather-container{
    padding: 7px;
  }
  .weather-icon {
    margin-bottom: 25px;
  }
  .current-day {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    min-height: 100vh;
  }
  .night {
    /* Zdjęcie autorstwa eberhard grossgasteiger z Pexels */
    background-image: url('../assets/night.jpg');
    color: #fafffd;
  }
  .day {
    /* Zdjęcie autorstwa Disha Sheta z Pexels */
    background-image: url('../assets/day.jpg');
    color: #fafffd;
  }
  .weather-icon {
    font-size: 6rem;
  }
  .weather-data, .location-data {
    padding-left: 10%;
  }
  .data-box {
    padding: 5px;
  }
  .data-box {
  }
  .temperature {
    font-size: 2.5rem;
  }
  .location-box {
    padding-top: 2px;
    padding-bottom: 2px;
  }
  .location-box:first-of-type {
    border-bottom: 2px solid #d1ab13;
  }
</style>
