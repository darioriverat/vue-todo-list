<template>
  <div id="app">
    <div class="container mt-5 jumbotron">
      <h2>Todo List</h2>
      <new-task :tasks="tasks"></new-task>
      <ul class="list-group">
        <li
          v-for="(task, index) in tasks"
          :key="task.text"
          class="list-group-item d-flex justify-content-between align-items-center"
        >
          <span :class="task.done ? 'done' : ''">{{ task.text }}</span>
          <div class="btn-group">
            <base-button type="success" @click="task.done = !task.done"
              >Check</base-button
            >
            <base-button type="danger" @click="deleteTask(index)">
              Delete
            </base-button>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import BaseButton from "./components/BaseButton";
import NewTask from "./components/NewTask";

export default {
  name: "App",
  components: {
    NewTask,
    BaseButton,
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
  methods: {
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
