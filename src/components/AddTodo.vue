<template>
  <div class="add-todo">
    <div class="card mt-3">
      <div class="card-body">
        <form @submit="onSubmit">
          <div class="form-group">
            <input type="text" v-model="title" class="form-control mb-3"  placeholder="Add Todo"/>
            <button type="submit" class="btn btn-primary">Submit</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    }
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
      this.title = ""
    }
  }
};
</script>

<style scoped>
</style>
