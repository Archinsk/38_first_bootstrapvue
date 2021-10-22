<template>
  <IconButtonSquare :icon="icon" :class="buttonSemantics" />
</template>

<script>
import IconButtonSquare from "../../../universal/IconButtonSquare";

export default {
  name: "CategoryButton",
  data() {
    return {
      buttonSemantics: "categoryButton",
    };
  },
  components: {
    IconButtonSquare,
  },
  props: ["icon"],
};
</script>

<style scoped>
.categoryButton {
  margin-right: 0.75rem;
  border-radius: 0.1875rem;
  background-color: deepskyblue;
  color: RGB(240, 255, 224);
}
</style>
