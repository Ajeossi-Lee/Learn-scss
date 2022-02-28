<template>
  <div>
    <h1>测试案例</h1>
    <hover-shadow></hover-shadow>
  </div>
</template>

<script>
import HoverShadow from '@/components/demos/HoverShadow.vue'

export default {
  components: { HoverShadow },
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
h1 {
  text-align: center;
}
</style>
