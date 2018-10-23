<template>
    <div>
        <p> Completed Tasks: {{ todos.filter(todo =>  { return todo.done == true}).length }}</p>
        <p>Pending Tasks: {{ todos.filter(todo =>  { return todo.done == false}).length }} </p>  
        <to-do-view v-for="(todo, index) in todos" :key="index" 
        :todo.sync="todo" 
        v-on:complete-todo="completeTodo" 
        v-on:delete-todo="deleteTodo"></to-do-view>     
    </div>
</template>

<script>
import ToDoView from "./ToDoView.vue";
export default {
  props: ["todos"],
  components: {
    ToDoView
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    }
  }
};
</script>

<style scoped>
</style>