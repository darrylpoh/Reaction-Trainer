<template>
  <div class="space" v-if="showSpace" @click="stopTimer">
      Click me!
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showSpace: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
         this.showSpace = true,
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
            console.log(this.reactionTime)

        }
    }
}
</script>

<style>
 .space {
     width: 400px;
     border-radius: 20px;
     background: #f4f4;
     color: black;
     text-align: center;
     padding: 100px 0;
     margin: 40px auto;

 }

</style>