<template>
  <footer class="footer">
    <div class="container footer__container">
      <div class="copyright"><p>INTELLIGENZA CONCIERGE SERVICES L.L.S. © 2022</p></div>
      <div class="mail"><a href="mailto:intelegenza_22@protonmail.com">intelegenza_22@protonmail.com</a></div>
    </div>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@use '@/assets/styles/helpers/media';
@use '@/assets/styles/helpers/helpers';
@use '@/assets/styles/helpers/grid';

.footer {
  background-color: var(--c-grey100);
  width: 100%;
  height: 20vh;
 padding: 30px 0;
  @include media.xl-only {
    height: 40vh;
    padding: 180px 0 40px 0;
    clip-path: polygon(0 0, 100% 25%, 100% 100%, 0 100%);
    margin-top: -100px;
  }
}

.footer__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.copyright {
  margin-bottom: 20px;

  p {
    font-size: 16px;
    color: var(--c-primary);

    @include media.xl-only {
      max-width: 500px;
      font-size: 22px;
      letter-spacing: .5rem;
    }
  }
}

a {
  @extend %hover-animation;
  max-width: 300px;
  font-size: 14px;

  @include media.xl-only{
    font-size: 22px;
    color: var(--c-primary);
    letter-spacing: .5rem;
    transition: all ease-in-out .4s;
  }


}
</style>
