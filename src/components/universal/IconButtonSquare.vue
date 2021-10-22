<template>
  <button class="iconButtonSquare" @click="$emit('handler')">
    <span class="material-icons">{{ icon }}</span>
  </button>
</template>

<script>
export default {
  name: "IconButtonSquare",
  data() {
    return {};
  },
  props: ["icon"],
};
</script>

<style scoped>
.iconButtonSquare {
  padding: 0;
  border: none;
  cursor: pointer;
}

.material-icons {
  padding: 0.6875rem;
  margin-right: 0;
}
</style>
