<template>
  <div>
    <div class='container'>
      <input v-model='computedMessage' type='text'/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LeftBar',
  props: {
    message: String,
  },
  computed: {
    computedMessage: {
      get() {
        return this.message;
      },
      set (newValue) {
        this.$emit('changed', newValue);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  padding: 2px;
  box-sizing: border-box; /* Subtract padding from height */
  display: flex;
  flex-direction: column;
  width: 100px;
  height: 100%;
  background-color: red;
}
input {
  text-align: center;
  font-size: 20pt;
}
</style>