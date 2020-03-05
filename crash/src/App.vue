<template>
  <div id="app">
    <Header />
    <AddToDo v-on:add-todo="addToDo"/>
    <ToDos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>

import Header from './components/layout/Header';
import ToDos from './components/ToDos';
import AddToDo from './components/AddToDo';

export default {
  name: 'App',
  components: {
    Header,
    ToDos,
    AddToDo
  },
  data () {
    return {
      todos: [
        {
          id: 1,
          title: "todo one",
          completed: false
        },
        {
          id: 2,
          title: "todo two",
          completed: true
        },
        {
          id: 3,
          title: "todo three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addToDo(newToDo) {
      this.todos = [...this.todos, newToDo];
    }
  }
}
</script>

<style lang="scss">
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
</style>
