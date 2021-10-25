<template>
  <b-alert show>
    <div class="itemWithCategory">
      <b-button class="categoryButton">
        <span class="material-icons">{{ taskItem.icon }}</span>
      </b-button>
      {{ taskItem.task }}
    </div>
    <b-button class="closeButton">
      <span class="material-icons">close</span>
    </b-button>
  </b-alert>
</template>

<script>
export default {
  name: "TaskItem",
  data() {
    return {
      iconName: "close",
    };
  },
  props: ["taskItem"],
};
</script>

<style lang="scss" scoped>
.alert {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: RGB(240, 255, 224);
  color: RGB(80, 80, 80);
  border-color: RGB(128, 128, 128);
  padding: 0;
  margin-bottom: 0.25rem;

  .itemWithCategory {
    display: flex;
    align-items: center;
  }
}

.btn.categoryButton, .btn.closeButton {
  padding: 0;
  border: none;
}

.categoryButton {
  background-color: orangered;
  color: RGB(240, 255, 224);
  border-radius: 0.1875rem;
  margin-right: 0.75rem;
}

.btn.closeButton {
  background-color: transparent;
  color: RGB(128, 128, 128);
}

.material-icons {
  padding: 0.6875rem;
  margin-right: 0;
}
</style>
