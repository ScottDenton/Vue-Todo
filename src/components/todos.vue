<template>
  <div class='container'>
    <h1>Our todo list</h1>
    <h2>Enter your next todo</h2>
    <form @submit.prevent='addTodo'>
      <div class="input-group mb-3">
      <input type="text" id='todoInput' class="form-control" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1">
        <div class="input-group-prepend">
          <button class="btn btn-outline-secondary" type="button" id="button-addon1" @click.prevent='addTodo'>Add</button>
        </div>
      </div>
    </form>

    <hr>

    <h2>Here are all my TODO's</h2>
    <div class='todo-container'>
      <todo
        v-for='(todo, index) in todos'
        :key='index'
        :todo='todo'
        :index='index'
        @delete='deleteTodo'
      />
    </div>
  </div>
</template>

<script>
  import Todo from './todo.vue';
  export default {

    components: {
      Todo,
    },

    data() {
      return {
        todos: [],
      }
    },

    methods: {
      getTodo() {
        return document.getElementById('todoInput').value;
      },

      clearInput() {
        return document.getElementById('todoInput').value = '';
      },

      addTodo() {
        this.todos.push(this.getTodo());
        this.clearInput();
      },

      deleteTodo(ind) {
        this.todos.splice(ind, 1);
      }
    }

  }
</script>
