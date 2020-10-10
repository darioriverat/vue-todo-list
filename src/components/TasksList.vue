<template>
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
  methods: {
    deleteTask: function(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>
