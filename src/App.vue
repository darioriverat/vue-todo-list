<template>
  <div id="app">
    <nav-bar></nav-bar>

    <div class="container mt-5 jumbotron">
      <h2>Todo List</h2>
      <div class="input-group">
        <input
          type="text"
          placeholder="description"
          v-model="newTask"
          class="form-control"
        />
        <div class="input-group-append">
          <button type="button" class="btn btn-primary" @click="addTask()">
            Add Task
          </button>
        </div>
      </div>
      <ul class="list-group">
        <li
          v-for="(task, index) in tasks"
          :key="task.text"
          class="list-group-item d-flex justify-content-between align-items-center"
        >
          <span :class="task.done ? 'done' : ''">{{ task.text }}</span>
          <div class="btn-group">
            <button
              type="button"
              class="btn btn-success"
              @click="task.done = !task.done"
            >
              Check
            </button>
            <button
              type="button"
              class="btn btn-danger"
              @click="deleteTask(index)"
            >
              Delete
            </button>
          </div>
        </li>
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
      newTask: "",
    };
  },
  methods: {
    addTask: function() {
      if (this.newTask.trim()) {
        this.tasks.push({
          text: this.newTask,
          done: false,
        });
        this.newTask = "";
      }
    },
    deleteTask: function(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
.done {
  text-decoration: line-through;
}
</style>
