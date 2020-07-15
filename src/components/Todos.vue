<template>
  <div class="todos mt-3">
    <ul class="list-group">
      <li
        class="list-group-item mb-3"
        v-for="todo in allTodos"
        :key="todo.id"
        @dblclick="onDubbleClick(todo)"
      >
        <p v-bind:class="{ 'is-complete': todo.completed }">{{ todo.title }}</p>
        <i @click="deleteTodo(todo.id)" class="fa fa-trash"></i>
      </li>
    </ul>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDubbleClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      };
      this.updateTodo(updTodo);
    }
  },
  computed: mapGetters(["allTodos"]),

  created() {
    this.fetchTodos();
  }
};
</script>

<style scoped>
.is-complete {
  text-decoration: line-through;
}
li:hover {
  box-shadow: 0 2.8px 2.2px rgba(0, 0, 0, 0.034),
    0 6.7px 5.3px rgba(0, 0, 0, 0.048), 0 12.5px 10px rgba(0, 0, 0, 0.06),
    0 22.3px 17.9px rgba(0, 0, 0, 0.072), 0 41.8px 33.4px rgba(0, 0, 0, 0.086),
    0 100px 80px rgba(0, 0, 0, 0.12);
  cursor: pointer;
}
</style>
