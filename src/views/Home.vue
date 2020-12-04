<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import axios from 'axios'

import Todos from '../components/Todos'
import AddTodo from '../components/AddTodo'

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [],
    }
  },
  methods: {
    addTodo(newTodo) {
      const { title, completed } = newTodo

      axios
        .post('https://jsonplaceholder.typicode.com/todos', {
          title,
          completed,
        })
        .then(res => this.todos = [...this.todos, res.data])
        .catch(err => console.error(err))
    },
    deleteTodo(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(() => this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => console.error(err))
    },
  },
  created() {
    axios
      .get('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(res => this.todos = res.data)
      .catch(err => console.error(err))
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
  }

  .btn {
    background: lightgreen;
    font-size: 1.2;
    border: 0;
    padding: 1em 1.5em;
  }
</style>