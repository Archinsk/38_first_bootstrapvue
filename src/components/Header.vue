<template>
  <header>
    <div class="container">
      <img id="logo" src="../assets/img/lifeplan_logo.jpg" alt="" />
      <div>
        <b-button v-b-modal.optionsMenu class="menuButton">
          <span class="material-icons">menu</span>
        </b-button>
        <b-button v-b-modal.authForm class="menuButton">
          <span class="material-icons">logout</span>
        </b-button>
        <b-modal size="sm" id="optionsMenu" title="Меню категорий">
          <p class="my-4">Hello from modal!</p>
        </b-modal>
        <b-modal size="sm" id="authForm" title="Вход">
          <AuthorizationForm/>
        </b-modal>
      </div>
    </div>
  </header>
</template>

<script>
import AuthorizationForm from "./AuthorizationForm";
export default {
  name: "Header",
  data() {
    return {
      menu: "menu",
      logout: "logout",
    };
  },
  components: {
    AuthorizationForm,
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: RGB(96, 192, 96);
  color: white;

  div {
    display: flex;
    align-items: center;
    justify-content: space-between;

    #logo {
      height: 4.5rem;
    }

    .menuButton {
      padding: 0;
      border: 1px solid transparent;
      margin-left: 0.75rem;
      border-radius: 0.25rem;
      background-color: transparent;
      color: white;

      .material-icons {
        padding: 0.6875rem;
        margin-right: 0;
      }
    }
  }
}
</style>
