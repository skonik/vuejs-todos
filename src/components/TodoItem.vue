<template>
   <div>
       <p  v-bind:class="{ 'completed': todo.completed }">
           <input type="checkbox" v-model="todo.completed">
           {{ todo.title }}
           <input type="button" v-on:click="removeItem" value="x">

       </p>


   </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props: {
            todo: {
                type: Object,
                required: true
            },

        },
        methods: {
            removeItem() {
                this.$parent.$emit('remove-todo', this.todo);
            }
        }
    }
</script>

<style scoped>
    .completed {
        text-decoration: line-through;
    }

</style>