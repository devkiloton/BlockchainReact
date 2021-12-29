<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-fifth">
      <lateralBar/>
    </div>
    <div class="column is-four-fifths">
      <Form @onSaveTask="saveTask"/>
      <div class="list">
        <Task v-for="(task, index) in tasks" :key="index" :task="task"/>
        <box v-if="isListEmpty">
          Start a Task! You just need to type a description for you task and click on "Start" button. 💚
        </box>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Box from './components/Box.vue';
import Form from './components/Form.vue';
import LateralBar from './components/LateralBar.vue';
import Task from './components/Task.vue';
import ITask from './interfaces/ITask';
export default defineComponent({
  components: { LateralBar, Form, Task, Box },
  name: 'App',
  data(){
    return {
      tasks:  [] as ITask[]
    }
  },
  computed: {
    isListEmpty():boolean {
      return this.tasks.length === 0;
    }
  },
  methods:{
    saveTask(task:ITask){
      this.tasks.push(task)
    }
  }
});
</script>

<style>

</style>
