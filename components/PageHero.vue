<template>
  <div class="hero" :style="{'background-image': `url(${require(`~/assets/images/${image}`)})`}">
    <div class="container hero__container">
      <h2 class="hero__title">{{ title }}</h2>
      <p class="hero__subtitle">{{ subtitle }}</p>
      <AppBtn class="hero-btn" link="#contacts" text="Learn more"></AppBtn>
    </div>
  </div>
</template>
<script>

export default {
  name: 'PageHero',
  props: {
    title: {
      type: String,
      default: ''
    },
    subtitle: {
      type: String,
      default: ''
    },
    image: {
      type: String,
      default: ''
    }
}
}
</script>
<style lang="scss">
@use '@/assets/styles/helpers/media';
@use '@/assets/styles/helpers/grid';

.hero {
  background-size: cover;
  background-position: center 100%;
  position: relative;
}

.hero__container {
  padding-top: 200px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.hero__title,
.hero__subtitle {
  color: var(--c-grey00);
  margin: 0;
  font-weight: 600;
  max-width: 500px;
  filter: drop-shadow(.115em .115em .115em black);
}

.hero__title {
  font-size: 22px;

  @include media.sm-to-md {
    font-size: 32px;
    letter-spacing: .5rem;
    max-width: 300px;
  }

  @include media.md-up {

    font-size: 42px;
    line-height: 110%;
    letter-spacing: 1rem;
  }
}

.hero__subtitle {
  font-size: 24px;
  color: var(--c-grey00);

  @include media.md-down {
    font-size: 14px;
    max-width: 300px;
  }
}

.hero-btn {
  margin-top: 100px;
  margin-bottom: 150px;
}
</style>
