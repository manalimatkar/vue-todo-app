<template>
  <div id="app">
    <create-to-do @create-todo="addTodo"></create-to-do>
    <to-do-list :todos="todos" ></to-do-list>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList.vue';
import CreateToDo from './components/CreateToDo.vue';
export default {
  name: 'app',
  components: {
    ToDoList,
    CreateToDo
  },
   data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.push({
        title : todo.title,
        project: todo.project,
        done: false
      });
    },
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
