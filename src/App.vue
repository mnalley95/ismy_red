<template>
  <div class="attribution">
    Code adapted from <a href="https://ismy.blue" target="_blank">ismy.blue</a>
  </div>
  <BlueGreenTest />
</template>

<script>
import BlueGreenTest from './components/BlueGreenTest.vue'

export default {
  name: 'App',
  components: {
    BlueGreenTest
  }
}
</script>


<style>
html,
body,
#app {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
</style>