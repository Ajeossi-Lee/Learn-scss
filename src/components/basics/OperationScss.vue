<template>
  <div>
    <h2>运算</h2>
    <p class="page">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam eveniet
      unde iste fugiat, vel laudantium dolorem.
    </p>
    <p class="page2">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Error, facilis.
    </p>
    <hr />
  </div>
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
$page-size: 40px;

.page {
  margin: 0 auto;
  height: 100px * 2;
  width: 100px + 100px;
  /* 
    / 在 CSS 中通常起到分隔数字的用途
    以下三种情况 / 将被视为除法运算符号：
      如果值，或值的一部分，是变量或者函数的返回值
      如果值被圆括号包裹
      如果值是算数表达式的一部分
   */
  font-size: ($page-size / 2);
  // + 可用于连接字符串
  cursor: not- + allowed;
}

// 插值语句
$name: page2;
$bgc: background;
.#{$name} {
  #{$bgc}-color: rgb(0, 255, 170);
}

hr {
  margin-top: 100px;
}
</style>
