<template>
  <div class="selected">
    <slot></slot>
    <div class="selected__list">
      <v-selected-item
        class="selected__item"
        v-for="item in items"
        :key="item.id"
        :item="item"
      />
    </div>
  </div>
</template>

<script>
import VSelectedItem from "./VSelectedItem.vue";
export default {
  name: "VSelected",
  components: {
    VSelectedItem,
  },
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
