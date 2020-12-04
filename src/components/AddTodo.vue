<template>
  <div>
    <form @submit="addTodo">
      <input class="text-input" type="text" v-model="title" name="title" placeholder="Add Todo...">
      <input type="submit" value="Add" class="btn">
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
    }
  },
  methods: {
    addTodo(event) {
      event.preventDefault()

      const newTodo = {
        title: this.title,
        completed: false,
      }

      this.$emit('add-todo', newTodo)

      // empty input after submission
      this.title = ''
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
    width: 100%;
  }

  .text-input {
    flex-grow: 1;
    border: 0;
    padding: .5em;
    border-radius: 0;
  }
</style>