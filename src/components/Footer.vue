<template>
  <!-- Footer -->
  <footer class="page-footer font-small rgba-black-strong fixed-bottom">
    <div class="container-fluid">
      <div class="row" v-if="exist">
        <NextDay class="next-day col-3" v-for="(d, index) in days" :key="index" :day="d" />
      </div>
    </div>
  </footer>
</template>

<script>
import NextDay from './NextDay';

export default {
  name: "Footer",
  props: ["days", "exist"],
  components: {
    NextDay
  }
};
</script>

<style scoped>

</style>
