<template>
  <router-view/>
</template>

<script lang="ts">
import {defineComponent, provide} from 'vue'
import {ref} from 'vue'
export default defineComponent({
  name: 'App',
 setup(){
    const asideVisible=ref(false)
    provide('asideVisible',asideVisible)
 }
})
</script>

<style>

</style>
