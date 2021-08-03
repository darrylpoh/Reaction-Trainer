<template>
  <h1>Reaction Trainer</h1>
  <button @click="start">begin</button>
</template>

<script>
export default {
  name: 'App',
  components: { },
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
      console.log(this.delay)
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
