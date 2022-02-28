<template>
  <div>
    <h1>测试结果展示</h1>
    <variate-scss></variate-scss>
    <operation-scss></operation-scss>
    <control-logic></control-logic>
    <nest-scss></nest-scss>
    <function-scss></function-scss>
    <extend-scss></extend-scss>
  </div>
</template>

<script>
import VariateScss from '@/components/basics/VariateScss.vue'
import OperationScss from '@/components/basics/OperationScss.vue'
import ControlLogic from '@/components/basics/ControlLogic.vue'
import NestScss from '@/components/basics/NestScss.vue'
import FunctionScss from '@/components/basics/FunctionScss.vue'
import ExtendScss from '@/components/basics/ExtendScss.vue'

export default {
  components: {
    VariateScss,
    OperationScss,
    ControlLogic,
    NestScss,
    FunctionScss,
    ExtendScss
  },
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
