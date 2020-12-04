<template>
  <header class="header">
    <h1>Todo list</h1>

    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style scoped>
  .header {
    background: #444;
    color: white;
    padding: 1em 2em;
  }

  #nav a {
    font-weight: bold;
    color: #fff;
  }

  #nav a.router-link-exact-active {
    color: #42b983;
  }
</style>