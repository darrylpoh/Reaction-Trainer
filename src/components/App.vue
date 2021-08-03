<template>
  <h1>Reaction Trainer</h1>
  <button @click="start" :disabled="isTraining">play</button>
  <box v-if="isTraining" :delay="delay" @end="endGame" />
  <p v-if="showResults">Reaction time: {{ score }} ms</p>
</template>

<script>
import box from './box.vue'

export default {
  name: 'App',
  components: { box },
  data() {
    return {
      isTraining: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
      // set time amount (ms)
      this.delay = 2000 + Math.random() * 5000
      this.isTraining = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isTraining = false
      this.showResults = true
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
  button {
    background: #f4f4;
    color: black;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    font-size: 16px;
    letter-spacing: 1px;
    cursor: pointer;
    margin: 10px;
  }
  button[disabled] {
    opacity: 0.2;
    cursor: not-allowed;
  }
</style>