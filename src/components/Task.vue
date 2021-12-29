<template>
  <Box class="box has-text-weight-bold">
      <div class="columns">
          <div class="column is-7">
              {{task.description||'Task without description'}}
          </div>
          <div class="column">
              <Timer :timeInSeconds="task.timeRangeInSeconds"/>
          </div>
      </div>
  </Box>
</template>

<script lang='ts'>
import { defineComponent, PropType } from 'vue';
import ITask from '../interfaces/ITask'
import Box from './Box.vue';
import Timer from './Timer.vue';
export default defineComponent({
  components: { Timer, Box },
    name: 'Task',
    props:{
        task:{
            type: Object as PropType<ITask>,
            required: true
        }
    }
})
</script>

<style>
.list{
    padding: 1.5rem;
}
</style>