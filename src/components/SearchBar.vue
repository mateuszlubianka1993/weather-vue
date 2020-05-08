<template>
  <!--Navbar-->
  <nav class="navbar navbar-expand-lg navbar-dark rgba-black-strong fixed-top">
    <form class="form-inline ml-auto" @submit.prevent="getData">
      <div class="container-fluid">
        <div class="row">
          <div class="col-8">
            <div class="md-form my-0">
              <input
                class="form-control-sm"
                type="text"
                placeholder="Search"
                aria-label="Search"
                v-model="city"
              />
            </div>
          </div>
          <div class="col-4">
            <button class="btn btn-outline-white btn-sm" type="submit">
              <i class="fas fa-search"></i>
            </button>
          </div>
        </div>
      </div>
    </form>
  </nav>
  <!--/.Navbar-->
</template>

<script>
export default {
  name: "SearchBar",
  data: function() {
    return {
      city: "",
      weather: {},
    };
  },
  methods: {
    getData() {

      this.$http.get(`https://api.openweathermap.org/data/2.5/forecast?q=${this.city}&APPID=26df753807a025c66570efc01c24fb39&units=metric`)
        .then( response => {
          return response.json();
        })
        .then(data => {
          this.weather = data;
          this.$emit('dataFetched', this.weather);
        })
      this.city = "";
    },
  },
};
</script>

<style scoped></style>
