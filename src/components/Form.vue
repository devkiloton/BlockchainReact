<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Form to create a new task">
        <input 
          type="text" 
          class="input" 
          placeholder="Which task do you want to do?"
          v-model="description"
          />
      </div>
      <div class="column">
        <TaskGenerator @onTimerEnd="finishTask"/>
      </div>
    </div>      
  </div>
</template>

<script lang='ts'>
import { defineComponent } from "vue";
import TaskGenerator from "./TaskGenerator.vue";
export default defineComponent({
  components: { TaskGenerator },
  name: 'Form',
  emits: ['onSaveTask'],
  data(){
    return{
      description: ''
    }
  },
  methods:{
    finishTask(timeRange: number):void{
      this.$emit('onSaveTask', {
        timeRangeInSeconds: timeRange,
        description: this.description
      })
      this.description = '';
    }
  }
})
</script>

<style>
.is-8{
  display: flex;
  align-items: center;
}
</style>