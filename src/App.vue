<template>
  <div id="app" ref="container"></div>
</template>

<script>
import * as THREE from "three";

export default {
  name: 'App',
  mounted() {},
  data() {
    return {
      scene: null,
      camera: null
    }
  },
  methods: {
    initScene() {
      // to do someting
    }
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
