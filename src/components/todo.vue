<template>
  <li> {{ todo }}
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

    methods: {
      deleteTodo() {
        this.$emit('delete', this.index);
      },
    },

  }
</script>