<template>
  <div class="selected-item">
    {{ item.name }}
  </div>
</template>

<script>
export default {
  name: "VSelected",
  props: {
    item: Object,
  },
};
</script>
<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
