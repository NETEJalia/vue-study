<template>
    <div>
        <form @submit="addToDo">
            <input v-model="title" type="text" name="title" placeholder="To Do">
            <input type="submit" value="submit" class="btn">
        </form>
    </div>
</template>

<script>

export default {
    name: 'AddToDo',
    data () {
        return {
            title: ''
        }
    },
    methods: {
        addToDo (e) {
            e.preventDefault();
            const newToDo = {
                id: 5,
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newToDo);

            this.title = '';
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>