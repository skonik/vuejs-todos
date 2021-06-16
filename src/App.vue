<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <TodoInput v-on:add-todo="addTodo"></TodoInput>
    <Todo v-bind:todos="todos"  v-on:remove-todo="removeItem"/>
  </div>
</template>

<script>
import Todo from './components/Todo.vue'
import TodoInput from "@/components/TodoInput";

export default {
  name: 'app',
  components: {
    Todo,
    TodoInput

  },

  data: function (){
    return {
      todos: JSON.parse(localStorage.getItem('todos'))
    };
  },

  methods: {
    addTodo(todo){

      this.todos.push(todo)
      localStorage.setItem('todos',  JSON.stringify(this.todos));
    },
    removeItem(todo){
      let todoIndex = this.todos.indexOf(todo);
      /* eslint-disable no-console */
      console.log(todoIndex);
      /* eslint-enable no-console */
      this.todos.splice(todoIndex, 1);
      localStorage.setItem('todos',  JSON.stringify(this.todos));
    }
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
  margin-top: 60px;
}
</style>
