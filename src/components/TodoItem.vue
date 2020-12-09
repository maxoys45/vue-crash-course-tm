<template>
  <div class="todo-item">
    <h3 class="title">{{ todo.title }}</h3>
    <button @click="deleteTodo(todo.id)" class="del">x</button>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    ...mapActions(['deleteTodo']),
  },
}
</script>

<style scoped>
  .todo-item {
    background: #eaeaea;
    border: 1px solid black;
    padding: 1em;
    display: flex;
    align-items: center;
  }

  .title {
    margin-left: 5px;
  }

  .del {
    background: red;
    color: white;
    border-radius: 2px;
    border: 0;
    width: 20px;
    height: 20px;
    margin-left: auto;
    flex-shrink: 0;
  }
</style>