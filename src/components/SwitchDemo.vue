<template>
  <div>
    <Switch :value="status" @input="status = $event" />
  </div>
</template>
<script lang="ts">
import { ref } from 'vue'
import Switch from '../libs/Switch.vue'
export default {
  components: { Switch },
  setup() {
    const status = ref(true)
    return {
      status
    }
  }
}
</script>
