<template>
  <div class="selected">
    <slot></slot>
    <div class="selected__list">
      <div class="selected__item" v-for="item in items" :key="item.id">
        {{ item.name }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "VSelected",
  props: {
    items: Array,
  },
};
</script>

<style scoped>
.selected {
  padding: 20px;
  border: 1px solid rgb(58, 58, 58);
}
.selected__list {
  display: flex;
  gap: 5px;
}
.selected__item {
  padding: 10px;
  border-radius: 5px;
  box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
}
</style>
