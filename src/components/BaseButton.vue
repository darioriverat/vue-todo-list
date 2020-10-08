<template>
  <button
    type="button"
    :class="['btn', className]"
    v-bind="$attrs"
    @click="$emit('click', $event)"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      required: true,
    },
  },
  computed: {
    className: function() {
      return `btn-${this.type}`;
    },
  },
};
</script>
