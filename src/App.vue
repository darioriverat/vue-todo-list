<template>
  <div id="app">
    <nav-bar></nav-bar>

    <div class="container mt-5">
      <h2>Todo List</h2>
      <input
        type="text"
        placeholder="description"
        v-model="newTask"
        class="form-control"
      />
      <button class="btn btn-primary" @click="addTask()">Add Task</button>
      <ul>
        <li v-for="task in tasks" :key="task.text">{{ task.text }}</li>
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
      newTask: null,
    };
  },
  methods: {
    addTask: function() {
      if (this.newTask.trim()) {
        this.tasks.push({
          text: this.newTask,
          done: false,
        });
      }
    },
  },
};
</script>

<style></style>
