<template>
  <div id="app">
    <Header/>
    <AddTodo/>
    <Todos v-bind:todos="todos" v-on:del-todo="delete_todo"/>
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        { id: 1, title: 'Todo One', completed: false },
        { id: 2, title: 'Todo Two', completed: true },
        { id: 3, title: 'Todo Three', completed: false }
      ]
    }
  },
  methods: {
    delete_todo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
  *, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: sans-serif;
    line-height: 1.4;
  }
</style>
