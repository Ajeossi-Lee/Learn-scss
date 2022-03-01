<template>
  <h2>demo2</h2>
  <div class="conf">
    <span class="dot" v-for="item of 100" :key="item"></span>
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
$colors1: #ffb6c1, #9932cc, #4169e1, #f0ffff, #f5deb3;
$colors2: #ffa07a, #b22222, #008000, #483d8b, #ff00ff;
$num: 100;

h2 {
  text-align: center;
}

.conf {
  position: relative;
  height: 600px;
  width: 100%;
  background-color: #001525;
  overflow: hidden;
}

@for $i from 1 through $num {
  $some: random($num);
  .dot:nth-of-type(#{$i}) {
    position: absolute;
    top: random($limit: 500) + px;
    left: random($limit: 800) + px;
    display: block;
    width: 15px;
    height: 15px;
    border-radius: 50%;
    background-color: nth($colors1, random(length($colors1)));
    opacity: random($limit: 100) / 100;
    animation: jump#{$i} 3s infinite ease-out;
    @if $some > ($num / 2) {
      animation-delay: random($limit: 3000) + ms;
    }
  }
}

@for $i from 1 through $num {
  @keyframes jump#{$i} {
    50% {
      transform: translate(random(1200) + px) translate(random(60) + px)
        scale(1.5) rotateX(180deg) rotateY(-180deg);
      border: 0;
      background-color: nth($colors2, random(length($colors2)));
    }
  }
}
</style>
