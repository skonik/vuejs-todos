<template>
    <form @submit.prevent="addTodo">
        <input type="text" v-model="title" name="title" class="title-input">
        <input type="submit" value="Submit" class="button-submit">
    </form>
</template>

<script>
    import uuid from 'uuid';
    export default {
        name: "TodoInput",
        data() {
            return {
                title: "",
            }
        },
        methods: {
            addTodo() {
                const newTodo = {
                    id: uuid.v4(),
                    title: this.title,
                    completed: false
                    };
                this.title = "";
                this.$emit('add-todo', newTodo);
            }
        }
    }
</script>

<style scoped>

  input {
    margin: 10px;
  }

  input:focus {
    outline: 3px dotted transparent;
    border-color: #42b983;

  }

  .button-submit {
    padding: 5px;
  }

  input[type=submit] {
    padding:5px 15px;
    background: #215854;
    border:0 none;
    cursor:pointer;
    -webkit-border-radius: 5px;
    border-radius: 5px;
    color: aliceblue;
  }

  input[type=submit]:hover {
    background: #55949d;
  }

</style>