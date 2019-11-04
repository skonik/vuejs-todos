<template>
    <form @submit.prevent="addTodo">
        <input type="text" v-model="title" name="title">
        <input type="submit" value="Submit">
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

</style>