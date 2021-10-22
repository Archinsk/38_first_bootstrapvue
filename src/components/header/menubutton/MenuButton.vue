<template>
  <IconButtonSquare
    :icon="icon"
    :semantics="buttonSemantics"
    :class="buttonSemantics"
  />
</template>

<script>
import IconButtonSquare from "../../universal/IconButtonSquare";

export default {
  name: "MenuButton",
  data() {
    return {
      buttonSemantics: "menuButton",
    };
  },
  components: {
    IconButtonSquare,
  },
  props: ["icon"],
};
</script>

<style scoped>
.menuButton {
  margin-left: 0.75rem;
  border-radius: 0.25rem;
  background-color: transparent;
  color: white;
}
</style>
