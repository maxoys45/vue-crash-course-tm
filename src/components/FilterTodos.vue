<template>
  <div class="filter">
    Filter todos:

    <select @change="filterTodos($event)" name="" id="">
      <option value="200">200</option>
      <option value="100">100</option>
      <option value="50">50</option>
      <option value="10">10</option>
      <option value="5">5</option>
    </select>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  name: 'FilterTodos',
  methods: mapActions(['filterTodos']),
}
</script>

<style scoped>
  .filter {
    border-bottom: 2px solid black;
    padding: 1em;
  }
</style>