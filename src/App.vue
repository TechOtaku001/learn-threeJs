<template>
  <div id="app">
    <demo />
  </div>
</template>

<script>
import Demo01 from "./components/Demo01";
export default {
  name: 'App',
  components: {
    'Demo': Demo01
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
