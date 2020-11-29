<template>
  <router-view></router-view>
</template>

<script lang="ts">
import { provide, ref } from 'vue'
import { router } from './router'
export default {
  name: 'App',
  setup() {
    const windowWidth = document.documentElement.clientWidth
    const asideVisible = ref(windowWidth <= 500 ? false : true)
    provide('asideVisible', asideVisible)
    router.afterEach(() => {
      if (windowWidth <= 500) {
        asideVisible.value = false
      }
    })
  }
}
</script>
