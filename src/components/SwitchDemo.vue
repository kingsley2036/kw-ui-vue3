<template>
  <div>
   <Switch :value="checked"  @input="checked=$event"/>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import Switch from '../lib/Switch.vue'
export default defineComponent({
  setup() {
    const checked=ref(false)
    return {checked}
  },
  components:{Switch}
})
</script>
