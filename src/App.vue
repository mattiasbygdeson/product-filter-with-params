<template>
  <div id="app">
    <h1>Router Test</h1>
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/products">Products</router-link></li>
    </ul>
    <router-view></router-view>
  </div>
</template>

<script>

export default {
  name: 'app',
}
</script>

<style>
body {
  color: rgb(243, 248, 250);
  background-color: #18191a;
}

a {
  color: rgb(22, 221, 138);
}

a:hover {
  color: rgb(221, 175, 22);
}

ul {
  padding: 0;
}

li {
  list-style: none;
  display: inline-block;
  margin-right: 20px;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>
