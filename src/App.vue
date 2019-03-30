<template>
  <div id="app">
    <Layout/>
  </div>
</template>

<script>
import Layout from './layouts/Layout.vue'

export default {
  name: 'app',
  components: {
    Layout
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
html, body, #app {
  width: 100%;
  height: 100%;
}
</style>
