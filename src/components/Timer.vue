<template>
  <section>
      <strong>{{time}}</strong>
  </section>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'
export default defineComponent({
    name: 'Timer',
    props: {
        timeInSeconds:{
            type: Number,
            default: 0
        }
    },
  computed:{
    time(): string{
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11,8);
    }
  }
})
</script>

<style>

</style>