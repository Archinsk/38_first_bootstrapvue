<template>
  <div class="my-2">
    <b-input-group>
      <b-form-input
        placeholder="Введите текст задачи..."
        v-model="addTaskInputValue"
      ></b-form-input>
      <b-input-group-append>
        <b-button class="p-0" @click="addNewTask">
          <span class="material-icons">{{ iconName }}</span>
        </b-button>
      </b-input-group-append>
    </b-input-group>
  </div>
</template>

<script>
export default {
  name: "AddTaskForm",
  data() {
    return {
      iconName: "add",
      addTaskInputValue: "",
    };
  },
  props: [],
  methods: {
    addNewTask() {
      // function ajaxGetRequest() {
      //   let xhr = new XMLHttpRequest();
      //   xhr.responseType = "json";
      //   xhr.onreadystatechange = function () {
      //     if (this.readyState === 4 && this.status === 200) {
      //       console.log(this.response);
      //     }
      //   };
      //   xhr.open("GET", "https://jsonplaceholder.typicode.com/todos");
      //   xhr.setRequestHeader(
      //     "Content-type",
      //     "application/x-www-form-urlencoded"
      //   );
      //   xhr.send();
      // }
      // ajaxGetRequest();
      function ajaxPostRequest(url, requestText) {
        let xhr = new XMLHttpRequest();
        xhr.onreadystatechange = function () {
          if (this.readyState === 4 && this.status === 200) {
            console.log(this.response);
          }
        };
        xhr.open("POST", url, true);
        xhr.setRequestHeader(
          "Content-type",
          "application/x-www-form-urlencoded"
        );
        xhr.send(requestText);
      }
      ajaxPostRequest("https://www.d-skills.ru/15_ajax/php/createTask.php", "inputTask=Тестовое_задание");

      this.$emit("add-task", this.addTaskInputValue);
      this.addTaskInputValue = "";
    },
  },
};
</script>

<style lang="scss" scoped>
.form-control {
  border-color: RGB(128, 128, 128);
  height: calc(2.875rem + 2px);

  &:focus {
    box-shadow: none;
    border-color: RGB(128, 128, 128);
  }
}

.btn {
  background-color: RGB(96, 192, 96);
  border: 1px solid RGB(128, 128, 128);
  border-radius: 0 0.25rem 0.25rem 0;
  &:hover {
    background-color: RGB(96, 192, 96);
  }
  &:focus {
    box-shadow: none;
    background-color: RGB(96, 192, 96);
    border-color: RGB(128, 128, 128);
  }
  &:not(.disabled):not(.disabled):active {
    background-color: RGB(96, 192, 96);
    &:focus {
      box-shadow: none;
    }
  }
}
.material-icons {
  padding: 0.6875rem;
  margin-right: 0;
}
</style>
