<template>
  <div class="current-day d-flex align-items-center" v-bind:class = "(timeOfDay === 'day') ? 'day' : 'night'">
    <div class="weather-container container">
      <div class="weather-icon text-center">
        <i v-if="timeOfDay === 'day'" class="fas fa-cloud-sun"></i>  <i v-else class="fas fa-cloud-moon"></i>
      </div>
      <div class="weather-data container">
        <div class="row">
          <div class="data-box temperature">
            16&ordm;C
          </div>
          <div class="data-box d-flex flex-column justify-content-between">
            <div class="wind text-justify">112km/h</div>
            <div class="humidity text-justify">15%</div>
          </div>
          <div class="data-box description d-flex align-items-end">
            <span>Sunny</span>
          </div>
        </div>
      </div>
      <div class="location-data container text-justify">
        <div class="location-box">
          <i class="fas fa-map-marker-alt"></i> London
        </div>
        <div class="location-box d-flex justify-content-between">
          <div class="date">
            THU / May 07
          </div>
          <div class="time">
            17:09
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CurrentDay',
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
