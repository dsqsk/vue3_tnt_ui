<template>
  <div class="topnav">
    <span class="toggleAside" @click="toggleMenu"></span>
    <div class="logo">LOGO</div>
    <ul class="menu">
      <li>菜单1</li>
      <li>菜单2</li>
    </ul>
  </div>
</template>
<script lang="ts">
import { inject, Ref } from 'vue'
export default {
  setup() {
    const asideVisible = inject<Ref<boolean>>('asideVisible')
    const toggleMenu = () => {
      asideVisible.value = !asideVisible.value
    }
    return {
      toggleMenu
    }
  }
}
</script>
<style lang="scss" scoped>
.topnav {
  position: relative;
  z-index: 999;
  background: pink;
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  justify-content: center;
  align-items: center;
  .logo {
    max-width: 6em;
    margin-right: auto;
  }
  .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    li {
      margin: 0 1em;
    }
  }
  .toggleAside {
    width: 24px;
    height: 24px;
    background: #000;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
  }
  @media (max-width: 500px) {
    .menu {
      display: none;
    }
    .logo {
      margin: 0 auto;
    }
    .toggleAside {
      display: inline-block;
    }
  }
}
</style>
