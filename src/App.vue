<template>
  <div id="app">
    <todos/>
  </div>
</template>

<script>

import Todos from './components/todos.vue'

export default {
  name: 'App',
  components: {
    Todos,
  }
}
</script>

<style lang="scss">
  @import 'src/stylesheets/app.scss';
</style>