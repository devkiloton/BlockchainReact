<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Form to create a new task">
        <input type="text" class="input" placeholder="Which task do you want to do?"/>
      </div>
      <div class="column">
        <TaskGenerator/>
      </div>
    </div>      
  </div>
</template>

<script lang='ts'>
import { defineComponent } from "vue";
import TaskGenerator from "./TaskGenerator.vue";
export default defineComponent({
  components: { TaskGenerator },
  name: 'Form'
})
</script>

<style>

</style>