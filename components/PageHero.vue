<template>
  <div class="hero" :style="{'background-image': `url(${require(`~/assets/images/${image}`)})`}">
    <div class="container hero__container">
      <h2 class="hero__title">{{ title }}</h2>
      <p class="hero__subtitle">{{ subtitle }}</p>
      <AppBtn link="#contacts" text="Learn more"></AppBtn>
    </div>
  </div>
</template>
<script>

export default {
  name: 'PageHero',
  props: ['title','subtitle', 'image']
}
</script>
<style lang="scss">
@use '@/assets/styles/helpers/media';

.hero {
  height: 600px;
  background-size: cover;
  background-position: center 100%;
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
  font-size: 42px;
  line-height: 110%;
}

.hero__subtitle {
  font-size: 24px;
  color: var(--c-grey00)
}
</style>
