<template>
  <section class="container about">
    <div class="content">
      <h2 class="h2">ABOUT US</h2>
      <p>For ten years we have been providing rental services to our clients around the world
        During this time, our rental algorithm has learned to fully cover the needs of our customers in any aspect of
        the
        journey.</p>
      <p>Our partners are the leading companies of the world, as well as more than 10,000 premium clients from different
        countries.</p>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@use '@/assets/styles/helpers/media';
@use '@/assets/styles/helpers/grid';

.about {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
}

.content {
  padding: 20px 20px 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  position: relative;
  top: -100px;
  transform: translate(-50% -50%);
  background: var(--c-grey100);
  box-shadow: 0 5px 46px 14px rgba(84, 179, 214, .7);
  max-width: 1200px;
  margin: 0 auto;
}

.h2 {
  font-size: 24px;
  color: var(--c-grey00);
  text-align: center;
  margin: 40px 0 40px 0;

  @include media.md-up {
    font-size: 32px;
    letter-spacing: .3rem;
  }
}

p {
  max-width: 70%;
  color: var(--c-grey40);
  margin-bottom: 20px;
  text-align: justify;
  font-size: 14px;

  @include media.md-up {
    letter-spacing: .1rem;
    font-size: 18px;
  }

}


</style>
