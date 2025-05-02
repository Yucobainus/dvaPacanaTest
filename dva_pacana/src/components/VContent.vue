<template>
  <div class="content">
    <div class="content__list">
      <v-content-item
        class="content__item"
        v-for="product in products"
        :key="product.id"
        :product="product"
        @add-product="addProduct"
      />
    </div>
  </div>
</template>

<script>
import VContentItem from "./VContentItem.vue";
export default {
  name: "VContent",
  components: {
    VContentItem,
  },
  props: {
    products: Array,
  },
  methods: {
    addProduct(product) {
      this.$emit("addProduct", product);
    },
  },
};
</script>
<style scoped>
.content {
  border: 1px solid rgb(88, 88, 88);
  border-radius: 5px;
  padding: 15px;
}
.content__list {
  display: flex;
  flex-wrap: wrap;
  column-gap: 10px;
  row-gap: 20px;
}
</style>
