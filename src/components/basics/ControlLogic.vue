<template>
  <div>
    <h2>逻辑控制</h2>
    <p class="page">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam eveniet
      unde iste fugiat, vel laudantium dolorem.
    </p>
    <p class="page2">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Error, facilis.
    </p>
    <div>
      <ul>
        <li class="item1">Lorem, ipsum.</li>
        <li class="item2">Lorem, ipsum.</li>
        <li class="item3">Lorem, ipsum.</li>
      </ul>
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
// if条件判断
$type: matador;
.page {
  @if $type == ocean {
    color: blue;
  } @else if $type == matador {
    color: red;
  } @else if $type == monster {
    color: green;
  } @else {
    color: black;
  }
}
// @for循环
/* 
  @for $var from <start> through <end> 
  @for $var from <start> to <end> 不包含end
 */
@for $i from 1 through 3 {
  .item#{$i} {
    font-size: 1em * $i;
  }
}
// @each
/* 
  @each 指令的格式是 $var in <list>, $var 可以是任何变量名，比如 $length 或者 $name，而 <list> 是一连串的值，也就是值列表
 */
// @each $header, $size in (h1: 2em, h2: 1.5em, h3: 1.2em) {
//   #{$header} {
//     font-size: $size;
//   }
// }

// @while 指令重复输出格式直到表达式返回结果为 false。这样可以实现比 @for 更复杂的循环，只是很少会用到
// $i: 6;
// @while $i > 0 {
//   .item-#{$i} { width: 2em * $i; }
//   $i: $i - 2;
// }

hr {
  margin-top: 100px;
}
</style>
