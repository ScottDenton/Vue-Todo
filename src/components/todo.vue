<template>
  <li :class='{"completed": completed}'> {{ todo }}
    <span class='complete-text' @click='completed = !completed'> Complete </span>
    <span class='delete-text' @click='deleteTodo()'> Delete </span>
  </li>
</template>

<script>
  export default {

    props: {
      todo: {
        type: String,
      },
      index: {
        type: Number,
      }
    },

    data() {
      return {
        completed: false,
      };
    },

    methods: {
      deleteTodo() {
        this.$emit('delete', this.index);
      },
    },

  }
</script>