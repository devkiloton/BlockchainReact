<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" aria-label="Form to create a new task">
        <input type="text" class="input" placeholder="Which task do you want to do?"/>
      </div>
      <div class="column is-flex is-align-items-center is-justify-content-space-between">
        <section>
          <strong>{{time}}</strong>
        </section>
        <button class="button" @click="start">
          <span class="icon">
            <i class="fas fa-play"></i>
          </span>
          <span>Play</span>
        </button>
        <button class="button" @click="stop">
          <span class="icon">
            <i class="fas fa-stop"></i>
          </span>
          <span>Stop</span>
        </button>
      </div>
    </div>      
  </div>
</template>

<script lang='ts'>
import { defineComponent } from "vue";
export default defineComponent({
  name: 'Form',
  data() {
    return {
      timeInSeconds: 0,
      timerId: 0
    }
  },
  computed:{
    time(): string{
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11,8);
    }
  },
  methods: {
    start(){
      this.timerId = setInterval(() => this.timeInSeconds++, 1000)
    },
    stop(){
      clearInterval(this.timerId);
    }
  }
})
</script>

<style>

</style>