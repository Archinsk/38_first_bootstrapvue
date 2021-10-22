<template>
  <li
    class="alert alert-secondary alert-dismissible fade show mb-1"
    role="alert"
  >
    <CategoryButton :icon="taskItem.icon" />
    {{ taskItem.task }}
    <button
      type="button"
      class="btn-close"
      data-bs-dismiss="alert"
      aria-label="Close"
    ></button>
  </li>
</template>

<script>
import CategoryButton from "./categorybutton/CategoryButton";

export default {
  name: "TaskItem",
  props: ["taskItem"],
  components: {
    CategoryButton,
  },
};
</script>

<style scoped>
li {
  display: flex;
  align-items: center;
  background-color: RGB(240, 255, 224);
  color: RGB(80, 80, 80);
  border-color: RGB(128, 128, 128);
  padding: 0;
}

.btn-close {
  padding: 0.9375rem;
}

.btn-close:focus {
  box-shadow: none;
}
</style>
