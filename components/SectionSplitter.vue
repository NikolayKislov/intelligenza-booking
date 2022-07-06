<template>
  <section :class="`splitter`">
    <div :class="isColored? 'dark' : 'light'">
      <div class="container">
      <h2 class="title-dark">{{title}}</h2>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionSplitter',
  props: {
    isColored: {
      type: Boolean,
      default: false,
    },
    title: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.dark {
  clip-path: polygon(0 0, 0% 100%, 100% 100%);
  width: 100%;
  height: 40vh;
  background: var(--c-grey100);
}

.light {
  clip-path: polygon(0 0, 100% 0, 100% 100%);
  width: 100%;
  height: 40vh;
  background: var(--c-grey00);
}
.container {
  position: relative;
  z-index: 10;
  top: 250px;
  transform: translate (-50% - 50%);
}

.title-dark {
  font-size: 32px;
  color: var(--c-primary);
  z-index: 10;
  text-align: center;
  letter-spacing: .5rem;
}
</style>
