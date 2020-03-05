<template>
    <div>
        <div v-for="todo in todos" v-bind:key="todo.id">
            <ToDoItem v-bind:todo="todo"/>
        </div>
    </div>
</template>

<script>
import ToDoItem from './ToDoItem';

export default {
    name: 'todos',
    components: {
        ToDoItem
    },
    props: ["todos"]
} 
</script>

<style scoped>

</style>