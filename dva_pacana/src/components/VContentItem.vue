<template>
  <div class="item" @click="addProduct">{{ product.name }}</div>
</template>
<script>
export default {
  name: "VContentItem",
  props: {
    product: Object,
  },
  methods: {
    addProduct() {
      this.$emit("addProduct", this.product);
    },
  },
};
</script>

<style scoped>
.item {
  width: calc(100% / 4 - 30px);
  padding: 15px 10px;
  border-radius: 5px;
  box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
  font-size: 14px;
  transition: 0.5s ease;
  text-align: center;
}

.item:hover {
  cursor: pointer;
  box-shadow: 2px 2px 8px 0px rgba(34, 60, 80, 0.2);
}
</style>
