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
  data() {
    return {
    todos: [
      {
        id: 0,
        title: 'test',
        completed: true
      },
      {
        id: 1,
        title: 'test2',
        completed: false
      }
    ]
    }
  },
  methods: {
    addTodo(todo){

      this.todos.push(todo)
    },
    removeItem(todo){
      let todoIndex = this.todos.indexOf(todo);
      /* eslint-disable no-console */
      console.log(todoIndex);
      /* eslint-enable no-console */
      this.todos.splice(todoIndex, 1);
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
