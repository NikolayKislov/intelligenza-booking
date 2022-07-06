<template>
  <div class="splash">
    <div class="splash__title-box">
      <span class="title-box__top">INTEL</span>
      <span class="title-box__bottom">LIGENZA</span>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.splash {
  width: 100%;
  height: 100vh;
  position: relative;
  animation: screen-transition 10s;
  background: black;
}
.splash__title-box {
  position: absolute;
  width: fit-content;
  top: 40%;
  left: calc(50% - 249px);
}

span {
  color: white;
  font-size: 64px;
  font-weight: bold;
}

.title-box__top {
  position: relative;
  animation: text-animation-top;
  animation-duration: 6s;
  animation-delay: .7s;
}

.title-box__bottom {
  position: relative;
  animation: text-animation-bottom;
  animation-duration: 6s;
  animation-delay: .7s;
}


// animations

@keyframes screen-transition {
  0% {
    background-color: #fff;
    z-index: 10;
  }

  60% {
      background-color: black;
    }

  100% {
    z-index: -1;
  }
}

@keyframes opacity-animation {
  0% {
    visibility: hidden;
  }
  20%{
    visibility: visible;
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes text-animation-top {
  0% {
    visibility: hidden;
  }
  20% {
    visibility: visible;
    opacity: 0;
    top: -100px;
  }

  60% {
    opacity: 1;
    top: 0;
  }
  100% {
    transform: scale(500%);
  }
}

@keyframes text-animation-bottom {
  0% {
    visibility: hidden;
  }
  20%{
    visibility: visible;
    opacity: 0;
    bottom: -100px;
  }
  60% {
    opacity: 1;
    bottom: 0;
  }
  100% {
    transform: scale(500%);
  }
}
</style>
