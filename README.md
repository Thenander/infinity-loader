# Infinity loader

This loader is dependent of the root font size (rem).
If `1rem` is equal to `16px` the loader is `60px` x `60px` (ie the default in most browsers.)

[Online DEMO](https://microlab.se/infinity-loader/)

## Usage

Copy and paste the following snippet in your **HTML** markup:

```
<div class="infinity-loader">
  <div>
    <div></div>
  </div>
  <div>
    <div></div>
  </div>
</div>
```

Copy and paste the following code-block in your **CSS** file:

```
.infinity-loader {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 3.75em;
  width: 7.1em;
}

.infinity-loader div {
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  width: 3.75em;
  height: 3.75em;
  position: absolute;
}

.infinity-loader div:nth-child(1) {
  left: 0;
  animation-name: infinity-spin-clip-left;
}

.infinity-loader div:nth-child(1) div {
  animation-name: infinity-spin-left;
}

.infinity-loader div:nth-child(2) {
  right: 0;
  animation-name: infinity-spin-clip-right;
}

.infinity-loader div:nth-child(2) div {
  animation-name: infinity-spin-right;
}

.infinity-loader div:nth-child(1) div,
.infinity-loader div:nth-child(2) div {
  box-sizing: border-box;
  width: 3.75em;
  height: 3.75em;
  border-top: 0.4em solid #000;
  border-right: 0.4em solid transparent;
  border-bottom: 0.4em solid transparent;
  border-left: 0.4em solid transparent;
  border-radius: 100vw;
  animation-duration: 0.5s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}

@keyframes infinity-spin-left {
  100% {
    transform: rotate(360deg);
  }
}

@keyframes infinity-spin-right {
  100% {
    transform: rotate(-360deg);
  }
}

@keyframes infinity-spin-clip-left {
  0% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
  12% {
    clip-path: inset(1.875em 0 0 0);
  }
  25% {
    clip-path: inset(1.875em 0 0 0);
  }
  37% {
    clip-path: inset(0 0 0 0);
  }
  50% {
    clip-path: inset(0 0 1.875em 0);
  }
  62% {
    clip-path: inset(0 0 1.875em 0);
  }
  75% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
  87% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
  100% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
}

@keyframes infinity-spin-clip-right {
  0% {
    clip-path: inset(0 0 1.875em 0);
  }
  12% {
    clip-path: inset(0 0 1.875em 0);
  }
  25% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
  37% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
  50% {
    clip-path: inset(1.875em 0 1.875em 0);
  }
  62% {
    clip-path: inset(1.875em 0 0 0);
  }
  75% {
    clip-path: inset(1.875em 0 0 0);
  }
  87% {
    clip-path: inset(0 0 0 0);
  }
  100% {
    clip-path: inset(0 0 1.875em 0);
  }
}
```

### Even easier if you use Sass!

Copy and paste the following code-block in your **SCSS** file:

```
$time: 1s;
$size: 3.75em;
$border-width: 0.4em;

.infinity-loader {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: $size;
  width: $size * 2 - $border-width;

  div {
    animation-duration: $time;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    width: $size;
    height: $size;
    position: absolute;
  }

  div:nth-child(1) {
    left: 0;
    animation-name: infinity-spin-clip-left;

    div {
      animation-name: infinity-spin-left;
    }
  }
  div:nth-child(2) {
    right: 0;
    animation-name: infinity-spin-clip-right;

    div {
      animation-name: infinity-spin-right;
    }
  }

  div:nth-child(1) div,
  div:nth-child(2) div {
    box-sizing: border-box;
    width: $size;
    height: $size;
    border-top: $border-width solid #000;
    border-right: $border-width solid transparent;
    border-bottom: $border-width solid transparent;
    border-left: $border-width solid transparent;
    border-radius: 100vw;
    animation-duration: $time/2;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
  }
}

@keyframes infinity-spin-left {
  100% {
    transform: rotate(360deg);
  }
}

@keyframes infinity-spin-right {
  100% {
    transform: rotate(-360deg);
  }
}

@keyframes infinity-spin-clip-left {
  0% {
    clip-path: inset($size/2 0 $size/2 0);
  }
  12% {
    clip-path: inset($size/2 0 0 0);
  }
  25% {
    clip-path: inset($size/2 0 0 0);
  }
  37% {
    clip-path: inset(0 0 0 0);
  }
  50% {
    clip-path: inset(0 0 $size/2 0);
  }
  62% {
    clip-path: inset(0 0 $size/2 0);
  }
  75% {
    clip-path: inset($size/2 0 $size/2 0);
  }
  87% {
    clip-path: inset($size/2 0 $size/2 0);
  }
  100% {
    clip-path: inset($size/2 0 $size/2 0);
  }
}

@keyframes infinity-spin-clip-right {
  0% {
    clip-path: inset(0 0 $size/2 0);
  }
  12% {
    clip-path: inset(0 0 $size/2 0);
  }
  25% {
    clip-path: inset($size/2 0 $size/2 0);
  }
  37% {
    clip-path: inset($size/2 0 $size/2 0);
  }
  50% {
    clip-path: inset($size/2 0 $size/2 0);
  }
  62% {
    clip-path: inset($size/2 0 0 0);
  }
  75% {
    clip-path: inset($size/2 0 0 0);
  }
  87% {
    clip-path: inset(0 0 0 0);
  }
  100% {
    clip-path: inset(0 0 $size/2 0);
  }
}
```

Use the **_Sass_** variables to set size and time.
