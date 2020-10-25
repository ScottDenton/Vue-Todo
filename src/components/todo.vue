<template>
<div id="Awesome" class="anim750">
<div class="reveal circle_wrapper">
		<div class="circle">Hello!</div>
	</div>
  <div class="sticky anim750">
<div class="front circle_wrapper anim750">
<div class="circle anim750"></div>
</div>
</div>
  <div class="card" style="width: 18rem;">
    <span class='delete-text' @click='deleteTodo()'> Delete </span>
    <div class="card-body" :class='{"completed": completed}'>
      <p class="card-text">{{ todo }}</p>
      <div>
        <span class='complete-text' @click='completed = !completed'> Complete </span>
        </div>
    </div>
  </div>
  <div class="sticky anim750">
  <div class="back circle_wrapper anim750">
    <div class="circle anim750"></div>
  </div>
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
