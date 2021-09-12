<template>
  <div class="card shadow">
    <img :src="'assets/images/' + product.gambar" class="card-img-top" />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>

      <p class="card-text">Harga : Rp.{{ product.harga }}</p>
      <router-link :to="'/menu/' + product.id" href="#" class="btn btn-success">
        <b-icon-plus-square></b-icon-plus-square> Add to cart</router-link
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style></style>
