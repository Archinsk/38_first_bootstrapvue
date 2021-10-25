<template>
  <div id="app">
    <Header />
    <div class="container">
      <AddTaskForm @add-task="addNewTask($event)" />
      <div class="taskList">
        <TaskItem v-for="item of items" :key="item.id" :taskItem="item" />
      </div>
    </div>
    <!--      -->
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
import Header from "@/components/Header";
import AddTaskForm from "@/components/AddTaskForm";
import TaskItem from "./components/TaskItem";
export default {
  name: "App",
  data() {
    return {
      items: [
        { id: 1, task: "Построить дом", done: false, icon: "stars" },
        { id: 2, task: "Посадить дерево", done: true, icon: "favorite" },
        { id: 3, task: "Вырастить сына", done: false, icon: "home" },
      ],
      // inputValue: ''
    };
  },
  components: {
    Header,
    AddTaskForm,
    TaskItem,
  },
  methods: {
    addNewTask(event) {
      let newTask = {
        id: this.items.length + 1,
        task: event,
        done: false,
        icon: "home",
      };
      this.items.push(newTask);
      this.inputValue = "";
    },
  },
};
</script>

<style lang="scss">
body {
  background-color: RGB(228, 244, 224);
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: RGB(228, 244, 224);
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
