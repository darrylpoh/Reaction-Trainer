<template>
  <div class="box" v-show="showbox" @click="stopTimer">
    Click!
  </div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      showbox: false,
      timer: null,
      reactionTime: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.showbox = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    }
  }
}
</script>

<style>
  .box {
    width: 400px;
    border-radius: 20px;
    background:  #f4f4;
    color: black;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>