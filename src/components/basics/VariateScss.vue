<template>
  <div>
    <h2>变量</h2>
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
// 定义变量
$f-color: pink;
$f-size: 20px;

.page2 {
  // 加入!global 改变全局变量
  $f-color: green !global;
  color: $f-color;
}

.page {
  color: $f-color;
  font-size: $f-size;
}

hr {
  margin-top: 100px;
}
</style>
