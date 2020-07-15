<template>
  <div id="app">
    <div class="container">
      <AddTodo/>
      <Todos/>
    </div>
  </div>
</template>

<script>
import AddTodo from './components/AddTodo.vue'
import Todos from './components/Todos.vue'
export default {
  name: 'App',
  components: {AddTodo, Todos},
};
</script>

<style>
body {
  background: #1a2980; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #26d0ce,
    #1a2980
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #26d0ce,
    #1a2980
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>
