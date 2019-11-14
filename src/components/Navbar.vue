<template>
  <div class="navbar">
    <div>
      <img src="../assets/nasa.png">
    </div>
    <h2>NASA Picture Data Base</h2>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'navbar',
  props: {
    msg: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

img {
  width: auto;
  height: 50px;
  margin-right: 50%;
}

.navbar {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 100%;
  margin: 0px;
  background-color: #f8f8f8;
  border-bottom: 1px solid #ececec;
  min-height: 50px;
  height: auto;
}
h2 {
  margin: 0px;
}
</style>
