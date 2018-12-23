<template>
  <div id="app">
    <myheader />
    <translator/>
  </div>
</template>

<script>
import myheader from './components/header.vue';
import translator from './components/translator.vue';
export default {
  name: 'app',
  components: {
    myheader,
    translator
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
