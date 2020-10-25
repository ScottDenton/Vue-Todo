<template>
  <div class="card" style="width: 18rem;">
    <div class="card-body" :class='{"completed": completed}'>
      <p class="card-text">{{ todo }}</p>
      <span class='complete-text' @click='completed = !completed'> Complete </span>
      <span class='delete-text' @click='deleteTodo()'> Delete </span>
    </div>
  </div>
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
