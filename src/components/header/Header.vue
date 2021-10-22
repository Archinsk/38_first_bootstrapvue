<template>
  <header>
    <div class="container">
      <img id="logo" src="../../assets/img/lifeplan_logo.jpg" alt="" />
      <div>
        <MenuButton :icon="menu" />
        <MenuButton :icon="logout" />
      </div>
    </div>
  </header>
</template>

<script>
import MenuButton from "./menubutton/MenuButton";

export default {
  name: "Header",
  data() {
    return {
      menu: "menu",
      logout: "logout",
    };
  },
  components: {
    MenuButton,
  },
};
</script>

<style scoped>
header {
  background-color: RGB(96, 192, 96);
  color: white;
}

header div {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

#logo {
  height: 4.5rem;
}

ul {
  list-style: none;
  padding-left: 0;
}
</style>
