<template>
  <div>
    <h2>继承</h2>
    <p class="page error">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam eveniet
      unde iste fugiat, vel laudantium dolorem.
    </p>
    <p class="page2 seriousError">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Error, facilis.
    </p>
    <p class="notice">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Error, facilis.
    </p>
  </div>
  <hr />
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
// @extend
.error {
  border: 1px solid #f00;
  background-color: #fdd;
}
.seriousError {
  @extend .error;
  border-width: 3px;
}

// @extend-Only 选择器
// 定义一套样式并不是给某个元素用，而是只通过 @extend 指令使用
%extreme {
  color: blue;
  font-weight: bold;
  font-size: 2em;
}

.notice {
  @extend %extreme;
}

hr {
  margin-top: 100px;
}
</style>
