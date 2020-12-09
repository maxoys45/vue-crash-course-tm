<template>
  <div>
    <div
      class="todo"
      v-bind:class="{'is-complete': todo.completed}"
      @dblclick="onDblClick(todo)"
      :key="todo.id"
      v-for="todo in allTodos"
    >
      <TodoItem v-bind:todo="todo" />
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  computed: mapGetters(['allTodos']),
  methods: {
    ...mapActions(['fetchTodos', 'updateTodo']),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed,
      }

      this.updateTodo(updTodo)
    },
  },
  created() {
    this.fetchTodos()
  },
  components: {
    TodoItem,
  },
}
</script>

<style>
.todo.is-complete {
  opacity: 0.5;
}

.todo.is-complete h3 {
  text-decoration: line-through;
}
</style>