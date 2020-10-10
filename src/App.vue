<template>
  <div id="app">
    <div class="container mt-5 jumbotron">
      <h2>Todo List</h2>
      <new-task :tasks="tasks" />
      <tasks-list :tasks="tasks" />
    </div>
  </div>
</template>

<script>
import NewTask from "./components/NewTask";
import TasksList from "./components/TasksList";

export default {
  name: "App",
  components: {
    NewTask,
    TasksList,
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

<style>
.done {
  text-decoration: line-through;
}
</style>
