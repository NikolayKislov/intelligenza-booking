<template>
  <div class="advantages__item">
    <img class="item__image" :src="require(`@/assets/images/icons/${image}`)" :alt="`${title}`">
    <h3 class="item__title">{{ title }}</h3>
    <p class="item__description">{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: 'AdvantagesItem',
  props: {
    image: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    description: {
      type: String,
      default: ''
    },
  }
}
</script>

<style lang="scss" scoped>
@use '@/assets/styles/helpers/media';
@use '@/assets/styles/helpers/grid';

.advantages__item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 35px;
  background: var(--c-grey100);
  width: 300px;
  height: 240px;
  text-align: center;
  padding: 20px 20px;

  @include media.md-up {
    justify-content: flex-start;
    gap: 25px;
    height: 270px;
  }
}
.item__image {
  width: 42px;
  height: 42px;

  @include media.md-up {
    width: 64px;
    height: 64px;
  }

}
.item__title {
  color: var(--c-grey00);
  font-size: 16px;

  @include media.md-up {
    font-size: 24px;
  }
}
.item__description {
  color: var(--c-grey40);
  font-size: 14px;

  @include media.md-up {
    font-size: 18px;
  }
}
</style>
