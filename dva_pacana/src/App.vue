<template>
  <section class="wrapper">
    <div class="selected-wrapper">
      <v-selected-block :items="currentUserProducts">
        <h1>User Current Products</h1>
      </v-selected-block>
      <v-selected-block :items="currentShopProducts">
        <h1>Shop Current Products</h1>
      </v-selected-block>
    </div>
    <div class="content">
      <v-content-block :products="userProducts" @addProduct="addUserProduct" />
      <v-content-block :products="shopProducts" @addProduct="addShopProduct" />
    </div>
  </section>
</template>

<script setup>
import VContentBlock from "./components/VContent.vue";
import VSelectedBlock from "./components/VSelected.vue";
import { useTestStore } from "./store/index";
const store = useTestStore();

const userProducts = store.userProducts;
const shopProducts = store.shopProducts;
const currentUserProducts = store.currentUserProducts;
const currentShopProducts = store.currentShopProducts;

function addUserProduct(product) {
  store.addUserProduct(product);
}
function addShopProduct(product) {
  store.addShopProduct(product);
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.wrapper {
  margin: 0 auto;
  max-width: 1200px;
  padding: 60px 0 0 0;
}
.content {
  display: flex;
  column-gap: 15px;
}

.selected-wrapper {
  display: flex;
  justify-content: space-between;
  margin-bottom: 100px;
}
</style>
