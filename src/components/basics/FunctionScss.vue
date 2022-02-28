<template>
  <div>
    <h2>函数</h2>
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
$pColor: orange green;
.page {
  background-color: nth($pColor, 1);

  // 字符串函数
  &::before {
    content: unquote($string: '"hello a1ee"');
  }

  &::after {
    content: to-upper-case('welcom');
  }
}

.page2 {
  color: purple;
  width: percentage(0.3);
  margin: 0 auto;
}

hr {
  margin-top: 100px;
}
</style>
