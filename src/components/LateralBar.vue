<template>
  <header>
      <h1>Tracker</h1>
  </header>
</template>

<script lang='ts'>
import {defineComponent} from 'vue'
export default defineComponent({
    name: 'LateralBar'
})
</script>

<style>
    header{
        display: flex;
        justify-content: center;
        background: #333333;
        width: 100%;
        height: 100vh;
    }
    h1{
        font-size: 40px;
        font-weight: 700;
        color: #2ECC71;
    }
    @media only screen and (max-width: 768px){
        header{
            padding: 2.5 rem;
            height: auto;
        } 
    }
</style>