<template>
  <div class="todo">
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo"></TodoItem>
    </div>
  </div>
</template>

<script>
  import TodoItem from "@/components/TodoItem";

export default {
  components: {
    TodoItem
  },

  name: 'Todo',
  props: {
    todos: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
