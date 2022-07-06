<template>
  <a class="btn" :href="link">{{ text }}</a>
</template>

<script>

export default {
  name: 'AppBtn',
  props: ['path', 'link', 'text']
}
</script>
<style lang="scss">
@use '../assets/styles/helpers/helpers';
@use '../assets/styles/helpers/media';

.btn {
  display: inline-block;
  padding: 20px 20px;
  cursor: pointer;
  border: 0;
  border-radius: var(--b-radius);
  color: #fff;
  text-transform: uppercase;
  text-align: center;
  font-size: 1rem;
  letter-spacing: .15rem;
  transition: all .3s;
  position: relative;
  overflow: hidden;
  z-index: 1;
  text-decoration: none;
  width: 250px;

  &:after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: var(--c-secondary);
    border-radius: var(--b-radius);
    z-index: -2;
  }

  &:before {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 100%;
    background-color: var(--c-secondary-dark);
    transition: all .3s;
    border-radius: var(--b-radius);
    z-index: -1;
  }

  &:hover {
    color: #fff;

    &:before {
      width: 100%;
    }
  }
}
</style>
