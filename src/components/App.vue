<template>
  <h1>Reaction Trainer</h1>
  <button @click="start" :disabled="isTraining">begin</button>
  <space v-if="isTraining" :delay="delay"/>
</template>

<script>
import Space from './Space.vue'


export default {
  name: 'App',
  components: { Space },
  data() {
    return {
      isTraining: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.delay = 1000 + Math.random() * 5000
      this.isTraining = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
