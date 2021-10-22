<template>
  <ul class="taskList">
    <TaskItem v-for="item of listItems" :key="item.id" :taskItem="item" />
  </ul>
</template>

<script>
import TaskItem from "./taskitem/TaskItem";

export default {
  name: "TaskList",
  props: ["listItems"],
  components: {
    TaskItem,
  },
};
</script>

<style scoped>
.taskList {
  list-style: none;
  padding-left: 0;
}
</style>
