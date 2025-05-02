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

<script>
import VContentBlock from "./components/VContent.vue";
import VSelectedBlock from "./components/VSelected.vue";
export default {
  name: "App",
  components: {
    VContentBlock,
    VSelectedBlock,
  },
  data() {
    return {
      userProducts: [
        {
          id: 1,
          name: "Shoes 1",
        },
        {
          id: 2,
          name: "Shoes 2",
        },
        {
          id: 3,
          name: "Shoes 3",
        },
        {
          id: 4,
          name: "Shoes 4",
        },
        {
          id: 5,
          name: "T-shirt 1",
        },
        {
          id: 6,
          name: "T-shirt 2",
        },
        {
          id: 7,
          name: "T-shirt 3",
        },
        {
          id: 8,
          name: "T-shirt 4",
        },
      ],
      shopProducts: [
        {
          id: 11,
          name: "Jacket 1",
        },
        {
          id: 12,
          name: "Jacket 2",
        },
        {
          id: 13,
          name: "Jacket 3",
        },
        {
          id: 14,
          name: "Jacket 4",
        },
        {
          id: 15,
          name: "Hoodie 1",
        },
        {
          id: 16,
          name: "Hoodie 2",
        },
        {
          id: 17,
          name: "Hoodie 3",
        },
        {
          id: 18,
          name: "Hoodie 4",
        },
      ],
      currentUserProducts: [],
      currentShopProducts: [],
    };
  },
  methods: {
    addUserProduct(product) {
      if (
        this.currentUserProducts.length < 6 &&
        !this.currentUserProducts.find(
          (userProduct) => product.id === userProduct.id
        )
      ) {
        this.currentUserProducts.push(product);
      }
    },
    addShopProduct(product) {
      this.currentShopProducts = [product];
    },
  },
};
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
