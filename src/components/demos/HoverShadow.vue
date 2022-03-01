<template>
  <h2>demo1</h2>
  <div class="btn-container">
    <h3>Simple hover effects with <span>box-shadow</span></h3>
    <div class="btns">
      <button class="fill">Fill in</button>
      <button class="pulse">Pulse</button>
      <button class="close">Close</button>
      <button class="raise">Raise</button>
      <button class="up">Fill up</button>
      <button class="slide">Slide</button>
      <button class="offset">Offset</button>
    </div>
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
$colors: (
  fill: #a972cb,
  pulse: #ef6eae,
  close: #ff7f82,
  raise: #ffa260,
  up: #e4cb58,
  slide: #8fc866,
  offset: #19bc8b
);

span {
  color: #f0e68c;
}

h2 {
  text-align: center;
}

h3 {
  margin-top: 200px;
}

.btn-container {
  height: 600px;
  text-align: center;
  color: #fff;
  background-color: hsl(235, 5%, 10%);
  overflow: hidden;

  @each $button, $color in $colors {
    .#{$button} {
      --color: #{$color};
      --hover: #{adjust-hue($color, 45deg)};
    }
  }

  button {
    padding: 15px 40px;
    margin: 10px;
    outline: none;
    border: 2px solid transparent;
    background-color: hsl(235, 5%, 10%);
    transition: all 0.3s linear;
    color: var(--color);
    border-color: var(--color);

    &:hover {
      border-color: var(--hover);
      color: #fff;
    }
  }

  .fill:hover {
    box-shadow: inset 0 0 0 32px var(--hover);
  }

  .pulse:hover {
    animation: pulse 0.7s linear;
  }

  @keyframes pulse {
    0% {
      box-shadow: 0 0 0 0 var(--hover);
    }
    100% {
      box-shadow: 0 0 0 32px rgba($color: #fff, $alpha: 0);
    }
  }

  .close:hover {
    box-shadow: inset -66px 0 0 0 var(--hover), inset 66px 0 0 0 var(--hover);
  }

  .raise:hover {
    box-shadow: 0 8px 8px -6px var(--hover);
    transform: translateY(-4px);
  }

  .up:hover {
    box-shadow: inset 0 -54px 0 0 var(--hover);
  }

  .slide:hover {
    box-shadow: inset 124px 0 0 0 var(--hover);
  }

  .offset {
    box-shadow: 5px 5px 0 0 var(--color), inset 5px 5px 0 0 var(--color);

    &:hover {
      box-shadow: 0 0 0 0 var(--hover), inset 120px 60px 0 0 var(--hover);
    }
  }
}
</style>
