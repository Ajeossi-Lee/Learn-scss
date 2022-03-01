<template>
  <div>
    <h1>测试案例</h1>
    <Hover-shadow></Hover-shadow>
    <Confetti></Confetti>
    <Color-bubbles></Color-bubbles>
  </div>
</template>

<script>
import HoverShadow from '@/components/demos/HoverShadow.vue'
import Confetti from '@/components/demos/Confetti.vue'
import ColorBubbles from '@/components/demos/ColorBubbles.vue'

export default {
  components: { HoverShadow, Confetti, ColorBubbles },
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
