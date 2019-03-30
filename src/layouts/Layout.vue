<template>
  <div class='container'>
    <div class='head'>Practice 0</div>
    <div class='body'>
      <LeftBar
       v-bind:message='message'
       v-on:changed='updateMessage' class='leftbar'/>
      <Center
       :message='message'
       @changed='updateMessage'
       class='center'/>
      <RightBar
       :message='message'
       class='rightbar'/>
    </div>
  </div>
</template>

<script>
import LeftBar from '@/components/LeftBar';
import Center from '@/components/Center';
import RightBar from '@/components/RightBar';

export default {
  name: 'Layout',
  data: () => {
    return {
      message: 'hello',
    }
  },
  components: {
    LeftBar,
    Center,
    RightBar,
  },
  methods: {
    updateMessage: function(newValue) {
      console.log(newValue)
      this.message = newValue;
      console.log(newValue);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
}
.head {
  background-color: lightblue;
  width: 100%;
  font-size: 20pt;
}
.body {
  display: flex;
  flex-grow: 1;
  background-color: gray;
  width: 100%;
}
.leftbar {
  height: 100%;
}
.center {
  flex-grow: 1;
  min-width: 300px;
  height: 100%;
}
.rightbar {
  height: 100%;
}
</style>