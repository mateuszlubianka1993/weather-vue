<template>
  <!--Navbar-->
  <nav class="navbar navbar-expand-lg navbar-dark rgba-black-strong fixed-top">
    <form class="form-inline ml-auto">
      <div class="container-fluid">
        <div class="row">
          <div class="col-8">
            <div class="md-form my-0">
              <input
                class="form-control-sm"
                type="text"
                placeholder="Search"
                aria-label="Search"
              />
            </div>
          </div>
          <div class="col-4">
            <button
              class="btn btn-outline-white btn-sm"
              type="submit"
            >
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
};
</script>

<style scoped></style>
