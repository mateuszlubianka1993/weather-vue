<template>
  <div class="current-day d-flex align-items-center">
    <div class="weather-container container">
      <div class="weather-icon text-center">
        <i class="fas fa-cloud-sun"></i>
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
  name: 'CurrentDay'
}
</script>

<style scoped>
  .weather-container{
    padding: 7px;
    /* background-color: red; */
  }
  .weather-icon {
    margin-bottom: 25px;
  }
  .current-day {
    background-color: green;
    /* Zdjęcie autorstwa Darius Krause z Pexels */
    background-image: url('../assets/day.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    min-height: 100vh;
  }
  .weather-icon {
    font-size: 6rem;
  }
  .weather-data, .location-data {
    padding-left: 10%;
  }
  .data-box {
    padding: 5px;
    /* border: 1px solid black; */
  }
  .data-box {
    /* font-size: 0.9rem; */
  }
  .temperature {
    font-size: 2.5rem;
  }
  .location-box {
    padding-top: 2px;
    padding-bottom: 2px;
  }
  .location-box:first-of-type {
    border-bottom: 2px solid #2c3e50;
  }
</style>
