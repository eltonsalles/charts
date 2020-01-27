<template>
  <div id="app">
    <radar />
  </div>
</template>

<script>
import Radar from './components/Radar.vue';

export default {
  name: 'app',

  components: {
    Radar,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  width: 75vw;
  margin: 0 auto;
}
</style>
