<template>
      <div class="column is-flex is-align-items-center is-justify-content-space-between">
        <Timer :timeInSeconds="timeInSeconds"/>
        <button class="button" @click="start" :disabled="timerRunning">
          <span class="icon">
            <i class="fas fa-play"></i>
          </span>
          <span>Play</span>
        </button>
        <button class="button" @click="stop" :disabled="!timerRunning">
          <span class="icon">
            <i class="fas fa-stop"></i>
          </span>
          <span>Stop</span>
        </button>
      </div>
</template>

<script>
import { defineComponent } from "vue";
import Timer from "./Timer.vue";
export default defineComponent({
  components: { Timer },
  emits: ['onTimerEnd'],
  name: 'TaskGenerator',
  data() {
    return {
      timeInSeconds: 0,
      timerId: 0,
      timerRunning: false
    }
  },
  methods: {
    start(){
      this.timerRunning = true;
      this.timerId = setInterval(() => this.timeInSeconds++, 1000)
    },
    stop(){
      this.timerRunning = false;
      clearInterval(this.timerId);
      this.$emit('onTimerEnd', this.timeInSeconds);
      this.timeInSeconds = 0;
    }
  }
})
</script>

<style>

</style>