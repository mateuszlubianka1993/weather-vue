<template>
  <div class="next-day col-3">
    <img
      :src="`http://openweathermap.org/img/wn/${day.data.weather[0].icon}.png`"
      alt="img"
    />
    <div class="div">
      {{ day.name }}
    </div>
    <!-- {{d.data.main.temp}} -->
  </div>
</template>

<script>
export default {
  name: "NextDay",
  props: ["day"]
};
</script>

<style scoped>
.next-day {
  margin-top: 7px;
  margin-bottom: 5px;
  border-right: 1px solid #d1ab13;
  font-size: 0.7rem;
}
.next-day:last-of-type {
  border: 0;
}
.next-day i {
  font-size: 1.4rem;
}
</style>
