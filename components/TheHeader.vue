<template>
  <header class="header">
    <div class="container header__container">
      <div class="header__logo logo"><h1><NuxtLink to="/">Advanced Mail System FZE</NuxtLink></h1></div>
      <div class="header__nav">
        <TheNav/>
        <div
            class="hamburger"
            @click="menuToggle"
            :class="{'hamburger--active': barsIsActive}"
        >
          <span class="hamburger__bar"></span>
          <span class="hamburger__bar"></span>
          <span class="hamburger__bar"></span>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'TheHeader',
  data: () => ({
    barsIsActive: false,
  }),
  methods: {
    menuToggle: function () {
      this.barsIsActive = !this.barsIsActive
      this.$nuxt.$emit('toggle-menu')
      document.querySelector('.body').classList.toggle('body--fixed')
    }
  }
}
</script>
<style lang="scss" scoped>
@use '../assets/styles/helpers/media';
@use '../assets/styles/helpers/helpers';

.header {
  position: sticky;
  top: 0;
  z-index: var(--z-top-30);
  background: var(--c-grey00);
  box-shadow: 0 0 20px 1px rgb(14 25 30 / 40%);
}

.header__container {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 20px;
  position: relative;
  width: 98%;
}

.hamburger {
  display: block;
  cursor: pointer;
  position: fixed;
  top: 10px;
  right: 20px;
  z-index: var(--z-top-30);

  @include media.md-up {
    display: none;
  }
}

.hamburger__bar {
  display: block;
  width: 25px;
  height: 3px;
  margin: 5px auto;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
  background-color: var(--c-primary);

  .hamburger--active & {
    &:nth-child(2) {
      opacity: 0;
      z-index: var(--z-top-30);
    }

    &:nth-child(1) {
      transform: translateY(8px) rotate(45deg);
    }

    &:nth-child(3) {
      transform: translateY(-8px) rotate(-45deg);
    }
  }
}

.header__logo {
  h1{
    margin: 0;
    padding: 5px 0 5px 0;
  }

  a {
    font-size: 20px;
    line-height: 200%;
    color: var(--c-primary);
    font-weight: 600;
    text-decoration: none;
    margin: 0;
    padding: 0;
    @include media.md-up {
      font-size: 32px;
    }
  }
}
</style>
