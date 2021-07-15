<template>
  <div class="topnav">
    <div class="logo" @click="toggleVisible">LOGO</div>
    <ul class="menu">
      <li>菜单1</li>
      <li>菜单2</li>
    </ul>
  </div>
</template>

<script>
import {inject} from "vue";

export default {
  name: "Topnav",
  setup(){
    const asideVisible=inject('asideVisible')
    const  toggleVisible=()=>{
      asideVisible.value=!asideVisible.value
    }
    return {
      asideVisible,
      toggleVisible
    }
  }
}
</script>

<style scoped lang="scss">
.topnav {
  background: pink;
  display: flex;
  padding: 16px;
  position: relative;
  z-index: 10;
  > .logo {
    max-width: 6em;
    margin-right: auto;
  }

  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    > li {
      margin: 0 1em;
    }
  }
}
</style>