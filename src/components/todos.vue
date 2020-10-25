<template>
  <div>
    <h1>Our todo list</h1>
    <h2>Enter your next todo</h2>
    <form>
    <div class="input-group mb-3">
      <input id='todoInput' type="text" class="form-control" placeholder="Recipient's username" aria-label="Recipient's username" aria-describedby="button-addon2">
      <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button" id="button-addon2" @click.prevent='addTodo' >Add</button>
      </div>
    </div>
    </form>

    <hr>

    <h2>Here are all my TODO's</h2>
    <ul>
      <todo
        v-for='(todo, index) in todos'
        :key='index'
        :todo='todo'
        :index='index'
        @delete='deleteTodo'
      />
    </ul>
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
