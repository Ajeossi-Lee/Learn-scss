<template>
  <h2>demo3</h2>
  <div class="cbub">
    <span class="bubble" v-for="item in 20" :key="item"></span>
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
$colors: #a32d70, #6e32a0, #dbd3d9, #d64369, #7a7de0, #ffa07a, #b22222, #008000;
$num: 20;

h2 {
  text-align: center;
}

.cbub {
  position: relative;
  height: 600px;
  width: 100%;
  background-color: #20181e;
  overflow: hidden;
}

@for $i from 1 through $num {
  .bubble:nth-of-type(#{$i}) {
    position: absolute;
    top: random($limit: 500) + px;
    left: random($limit: 1200) + px;
    display: block;
    height: 80px;
    width: 80px;
    border-radius: 50%;
    background-color: mix(
      nth($colors, random(length($colors))),
      nth($colors, random(length($colors)))
    );
    // box-shadow: inset 3px 3px 10px 6px #eedae5;
    opacity: 0.7;
    animation: float#{$i} 8s linear infinite;

    &::after {
      position: absolute;
      top: 4px;
      right: 5px;
      content: '';
      display: block;
      width: 70px;
      height: 70px;
      border-radius: 50%;
      border-right: 7px solid #fff;
      opacity: 0.19;
    }
  }
}

@for $i from 1 through $num {
  $movex: random(
      $limit: 500
    ) -
    200 +
    px;
  $movex2: random(
      $limit: 200
    ) -
    200 +
    px;

  $movey: random(
      $limit: 100
    ) -
    50 +
    px;
  $movey2: random(
      $limit: 300
    ) -
    100 +
    px;

  @keyframes float#{$i} {
    40% {
      transform: translateX($movex) translateY($movey);
    }
    60% {
      background-color: desaturate(
        $color: nth($colors, random(length($colors))),
        $amount: 20%
      );
    }
    80% {
      transform: translateX($movex2) translateY($movey2);
    }
  }
}
</style>
