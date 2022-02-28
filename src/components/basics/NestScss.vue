<template>
  <div>
    <h2>嵌套</h2>
    <div class="box">
      <p class="page">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
        eveniet unde iste fugiat, vel laudantium dolorem.
      </p>
      <p class="page2">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Error, facilis.
      </p>
      <p class="page3">Lorem ipsum dolor sit.</p>
      <a href="https://www.baidu.com">百度一下</a>
    </div>
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
$color: green;
/* 
  可以在变量的结尾添加 !default 给一个未通过 !default 声明赋值的变量赋值，
  此时，如果变量已经被赋值，不会再被重新赋值，但是如果变量还没有被赋值，则会被赋予新的值。
  $color: red !default;
 */

.box {
  .page {
    color: $color;
  }
  // 属性嵌套
  .page2 {
    font: {
      family: fantasy;
      size: 3em;
      weight: bold;
    }
  }
  a {
    text-decoration: none;
    // & 代表嵌套规则外层的父选择器
    &:hover {
      color: chocolate;
      text-decoration: underline;
    }
  }
}

@import '@/assets/css/nest-import.scss';

// 混合指令
// 定义混合指令 @mixin
@mixin large-text {
  font: {
    family: Arial;
    size: 20px;
    weight: bold;
  }
  color: #ff0000;
}

// ... 可以传入多个参数
@mixin box-shadow($shadow...) {
  -webkit-box-shadow: $shadow;
  -moz-box-shadow: $shadow;
  -o-box-shadow: $shadow;
  -ms-box-shadow: $shadow;
  box-shadow: $shadow;
}

@mixin set-box($direction) {
  padding-#{$direction}: 4px;
  margin-#{$direction}: 10px;
}

.box {
  .page3 {
    // 引用混合样式 @include
    @include large-text;
    @include set-box(top);
    @include box-shadow(-5px 0 5px orange, 5px 0 5px blue);
  }
}

hr {
  margin-top: 100px;
}
</style>
