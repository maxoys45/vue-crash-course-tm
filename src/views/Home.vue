<template>
  <div id="app">
    <FilterTodos />
    <AddTodo />
    <Todos />
  </div>
</template>

<script>
import FilterTodos from '../components/FilterTodos'
import AddTodo from '../components/AddTodo'
import Todos from '../components/Todos'

export default {
  name: 'Home',
  components: {
    FilterTodos,
    AddTodo,
    Todos,
  },
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