<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-fifth">
      <lateralBar/>
    </div>
    <div class="column is-four-fifths">
      <Form/>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Form from './components/Form.vue';
import LateralBar from './components/LateralBar.vue';

export default defineComponent({
  components: { LateralBar, Form },
  name: 'App'
});
</script>

<style>

</style>
