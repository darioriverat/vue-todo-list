<template>
  <div class="input-group">
    <input
      type="text"
      placeholder="description"
      v-model="newTask"
      class="form-control"
      @keyup.enter="addTask"
    />
    <div class="input-group-append">
      <base-button type="primary" @click="addTask()">Add Task</base-button>
    </div>
  </div>
</template>

<script>
import BaseButton from "./../components/BaseButton";

export default {
  components: {
    BaseButton,
  },
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
  data: function() {
    return {
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
  },
};
</script>
