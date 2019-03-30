<template>
  <div>
    <div class='container'>
      <div v-for='i in Array(n).keys()' v-bind:key='i' class='radio-collection'>
        <input :id='"radio" + i' type='radio' name="message" :value='i' v-model="computedMessage"/>
        <label :for='"radio" + i' class='radio'>{{ i }}</label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Center',
  data: () => {
    return {
      n: 1000,
    }
  },
  props: {
    message: String,
  },
  computed: {
    computedMessage: {
      get() {
        return this.message;
      },
      set (newValue) {
        this.$emit('changed', newValue.toString());
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-content: flex-start;
  height: 100%;
  background-color: aqua;
}
.radio {
  display: block;
  background-color: yellowgreen;
  text-align: center;
  width: 50px;
  height: 50px;
}
.radio-collection input[type="radio"] {
  display: none;
}
.radio-collection label:hover {
  background-color: #dfd;
}
.radio-collection input[type="radio"]:checked + label {
    background-color:#bfb;
    border-color: #4c4;
}
</style>