<template>
  <span>
    <Navbar></Navbar>
    <Search></Search>
  </span>
</template>

<script lang="ts">
import Vue from 'vue';
import Navbar from './components/Navbar.vue';
import Search from './components/Search.vue'

export default Vue.extend({
  name: 'App',

  components: {
    Search,
    Navbar,
  },

  data: () => ({
    //
  }),
});
</script>

<style>
body {
  margin: 0px;
  max-width: 375px;
}
</style>