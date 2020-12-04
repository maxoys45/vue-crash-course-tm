<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <input type="checkbox" v-on:change="markComplete">
    <h3 class="title">{{ todo.title }}</h3>
    <button class="del" @click="$emit('del-todo', todo.id)">x</button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    },
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

  .is-complete {
    opacity: 0.5;
  }

  .is-complete h3 {
    text-decoration: line-through;
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