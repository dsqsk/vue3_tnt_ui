<template>
  <button @click="toggle" :class="{ state }">
    <span></span>
  </button>
</template>

<script lang="ts">
import { ref } from 'vue'
export default {
  setup() {
    const state = ref(false)
    const toggle = () => {
      state.value = !state.value
    }
    return {
      state,
      toggle
    }
  }
}
</script>

<style lang="scss" scoped>
$h: 22px;
$h2: $h - 4px;
button {
  height: $h;
  width: $h * 2;
  border: none;
  background: gray;
  border-radius: $h/2;
  position: relative;
}
span {
  position: absolute;
  top: 2px;
  left: 2px;
  height: $h2;
  width: $h2;
  background: white;
  border-radius: $h2 / 2;
  transition: left 1s;
}
button.state {
  background: blue;
}
button.state span {
  left: calc(100% - #{$h2} - 2px);
}
</style>
