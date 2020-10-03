<template>
  <div id="app">
    <nav-bar></nav-bar>

    <div class="container mt-5">
      <h2>Todo List</h2>

      <ul>
        <li v-for="task in tasks" :key="task">{{ task.text }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import NavBar from "./components/NavBarComponent";

export default {
  name: "App",
  components: {
    NavBar,
  },
  data: function() {
    return {
      tasks: [
        {
          text: "Task 1",
          done: true,
        },
        {
          text: "Task 2",
          done: false,
        },
        {
          text: "Task 3",
          done: false,
        },
      ],
    };
  },
};
</script>

<style></style>
