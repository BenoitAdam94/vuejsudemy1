<!-- eslint-disable vue/no-use-v-if-with-v-for,vue/no-confusing-v-for-v-if -->
<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from './views/home.vue'


export default {
  name: 'App',
  components: {
    Home
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

.purple-background {
  background-color:purple;
}
</style>
