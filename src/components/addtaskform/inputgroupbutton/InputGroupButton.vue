<template>
  <div class="input-group-append">
    <IconButtonSquare
      :icon="icon"
      :class="buttonSemantics"
      @handler="formHandler"
    />
  </div>
</template>

<script>
import IconButtonSquare from "../../universal/IconButtonSquare";

export default {
  name: "InputGroupButton",
  data() {
    return {
      buttonSemantics: "inputGroupButton",
    };
  },
  components: {
    IconButtonSquare,
  },
  props: ["icon"],
  methods: {
    formHandler() {
      this.$emit("add-task-form");
    },
  },
};
</script>

<style scoped>
.inputGroupButton {
  background-color: RGB(96, 192, 96);
  color: white;
  border: 1px solid RGB(128, 128, 128);
  border-radius: 0 0.25rem 0.25rem 0;
}
</style>
