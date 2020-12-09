<template>
  <div>
    <form @submit="onSubmit">
      <input class="text-input" type="text" v-model="title" name="title" placeholder="Add Todo...">
      <input type="submit" value="Add" class="btn">
    </form>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
    }
  },
  methods: {
    ...mapActions(['addTodo']),
    onSubmit(event) {
      event.preventDefault()

      this.addTodo(this.title)
    }
  },
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