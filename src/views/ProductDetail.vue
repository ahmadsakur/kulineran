<template>
  <div class="product-detail">
    <Navbar />
    <div class="container">
      <!-- Breadcrumb -->
      <div class="row mt-5">
        <div class="col">
          <nav aria-label="breadcrumb bg-none">
            <ol class="breadcrumb">
              <li class="breadcrumb-item">
                <router-link to="/" class="text-dark breadcrumb-links"
                  >Home</router-link
                >
              </li>
              <li class="breadcrumb-item text-dark">
                <router-link to="/menu" class="text-dark breadcrumb-links"
                  >Menu</router-link
                >
              </li>
              <li class="breadcrumb-item active" aria-current="page">
                Food Detail
              </li>
            </ol>
          </nav>
        </div>
      </div>
      <!-- Product Detail -->
      <div class="row mt-3">
        <div class="col-md-6">
          <img :src="'../assets/images/' + food.gambar" class="img-fluid" />
        </div>
        <div class="col-md-6">
          <h4 class="font-weight-bold">
            {{ food.nama }}
          </h4>
          <hr />
          <h6>
            <strong>Rp.{{ food.harga }}</strong>
          </h6>
          <form action="">
            <div>
              <label for="amount" class="font-weight-bold">Amount</label>
              <input name="amount" type="number" class="form-control" />
            </div>
            <div class="mt-3">
              <label for="keterangan" class="font-weight-bold">Notes</label>
              <input
                name="keterangan"
                placeholder="ask for extra spice etc.."
                type="text"
                class="form-control"
              />
            </div>
          </form>
          <button type="submit" class="btn btn-success mt-4">
            <b-icon-plus></b-icon-plus>Add to Cart
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import axios from "axios";
export default {
  name: "ProductDetail",
  components: {
    Navbar,
  },

  data() {
    return {
      food: {},
    };
  },
  methods: {
    setFood(e) {
      this.food = e;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products/" + this.$route.params.id)
      .then((response) => this.setFood(response.data))
      .catch((error) => console.log("Gagal :", error));
  },
};
</script>

<style></style>
