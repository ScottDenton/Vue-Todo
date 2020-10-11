<template>
  <div>
    <h1>Our todo list</h1>
    <h2>Enter your next todo</h2>
    <form>
      <input id='todoInput' type="text">
      <button type='submit' @click.prevent='addTodo'>Add</button>
    </form>

    <hr>
    <h2>Here are all my TODO's</h2>
    <li
      v-for='(todo,ind) in todos'
      :key=ind> {{ todo }}
      <span class='delete-text' @click='deleteTodo(ind)'> Delete</span>
    </li>
  </div>
</template>

<script>
  export default {

    data() {
      return {
          todos: [],
      }
    },

    methods: {
      getTodo() {
        return document.getElementById('todoInput').value
      },

      clearInput() {
        return document.getElementById('todoInput').value = ''
      },

      addTodo() {
        this.todos.push(this.getTodo())
        this.clearInput();
      },
      
      deleteTodo(ind) {
        this.todos.splice(ind, 1);
      }
    }

  }
</script>