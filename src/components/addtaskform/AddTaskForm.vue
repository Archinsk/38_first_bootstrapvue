<template>
  <div class="input-group my-2">
<!--    <input-->
<!--      type="text"-->
<!--      class="form-control"-->
<!--      placeholder="Введите текст задачи..."-->
<!--      aria-label="Введите текст задачи..."-->
<!--      aria-describedby="button-addon2"-->
<!--      @input="onInputHandler"-->
<!--      v-model="addTaskInputValue"-->
<!--    />-->
<!--    <InputGroupButton-->
<!--      :icon="iconName"-->
<!--      @add-task-form="addNewTask"-->
<!--    />-->

    <b-input-group>
      <b-form-input></b-form-input>
      <b-input-group-append>
        <b-button variant="success"><span class="material-icons">{{ iconName }}</span></b-button>
      </b-input-group-append>
    </b-input-group>
  </div>
</template>

<script>
// import InputGroupButton from "./inputgroupbutton/InputGroupButton";

export default {
  name: "AddTaskForm",
  data() {
    return {
      iconName: "add",
      addTaskInputValue: "",
    };
  },
  props: [],
  components: {
    // InputGroupButton,
  },
  methods: {
    addNewTask() {
      this.$emit("add-task", this.addTaskInputValue);
      this.addTaskInputValue = "";
    },
    // onInputHandler() {
    //     this.$emit("change-input-value", this.addTaskInputValue)
    // }
  },
};
</script>

<style scoped>
.form-control {
  border-color: RGB(128, 128, 128);
  height: calc(2.875rem + 2px);
}
.form-control:focus {
  box-shadow: none;
}
.material-icons {
  padding: 0.6875rem;
  margin-right: 0;
}
</style>
