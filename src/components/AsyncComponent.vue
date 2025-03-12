<template lang="">
  <div>
    <AsyncComp />
  </div>
</template>
<script>
import { defineAsyncComponent } from 'vue'
const AsyncComp = defineAsyncComponent(() => {
  return import('./YouConpAsync.vue')
})
export default {
  components: { AsyncComp },
}
</script>
<style lang=""></style>
