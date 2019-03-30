<template>
  <div>
    <div class='container'>
      <span>{{ message }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RightBar',
  props: {
    message: String,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  width: 100px;
  height: 100%;
  background-color: yellow;
}
span {
  text-align: center;
  font-size: 20pt;
}
</style>