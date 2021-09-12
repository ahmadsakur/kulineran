<template>
  <div class="hero">
    <!-- desktop -->
    <div class="d-none d-md-block">
      <div class="row mt-4">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h1>
                <strong>Delicious Food</strong> <br />
                at your fingertips
              </h1>
              <p>Fresh food available arround, get yours now!</p>
              <router-link class="btn btn-success" to="/menu">
                Order Now <b-icon-arrow-right></b-icon-arrow-right>
              </router-link>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img :src="'/assets/images/ilustrasi.png'" width="100%" />
        </div>
      </div>
    </div>

    <!-- mobile -->
    <div class="d-sm-block d-md-none">
      <div class="row mt-4">
        <div class="col-md-6">
          <img :src="'/assets/images/ilustrasi.png'" width="100%" />
        </div>
        <div class="col-md-6 mt-4">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Delicious Food</strong> <br />
                at your fingertips
              </h2>
              <p>Fresh food available arround, get yours now!</p>
              <button class="btn btn-success">
                Order Now <b-icon-arrow-right></b-icon-arrow-right>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
};
</script>

<style></style>
