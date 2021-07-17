<template>
  <button :class="{checked:value}" @click="toggle"> <span></span> </button>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  props:{
    value:Boolean
  },
  setup(props, context) {
    // const checked=ref(false)
    const toggle=()=>{
    context.emit('input',!props.value)
      // checked.value=!checked.value
    }
    return {
      toggle
    }
  },
})
</script>


<style lang='scss'>
  $h: 22px;
  $h2: $h - 4px;
  button{
    height: $h;
    width: $h*2;
    border: none;
    background: grey;
    border-radius: $h/2;
    position: relative;
  }
  span{
    position: absolute;
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    background:white;
    border-radius: $h2 / 2;
    transition: left 250ms;
  } 
  button.checked{
    background: blue;
    span{
         left: calc(100% - #{$h2} - 2px);
    }
  }
</style>