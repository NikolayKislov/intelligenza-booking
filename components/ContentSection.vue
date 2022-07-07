<template>
  <section :id="id" class="content-section">
    <div class="content-bg" :style="{'background-image': `url(${require(`~/assets/images/${path}/${file}`)})`}"></div>
    <div class="description">
      <h2 class="description__title">{{ title }}</h2>
      <div class="description__content">
        <p v-for="item in descriptionItems" :key="item">{{ item }}</p>
        <AppBtn text="CONTACT US"
        link="#contacts"
        />
      </div>
    </div>
    <div class="description__items">
      <img v-for="item in imageItems" :key="item" :src="require(`@/assets/images/${path}/${item}`)" alt="item">
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContentSection',
  props: {
    id: {
      type: String,
      default: ''
    },
    path: {
      type: String,
      default: ''
    },
    file: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    imageItems: {
      type: Array,
      default() {
        return []
      }
    },
    descriptionItems: {
      type: Array,
      default() {
        return [];
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@use '@/assets/styles/helpers/media';

.content-section {
  position: relative;
  margin-top: 40px;

  @include media.xl-only {
    clip-path: polygon(0 0, 100% 10%, 100% 100%, 0 90%);
    margin-top: 0;
  }
}

.content-bg {
  width: 100vw;
  height: 100vh;
  background-size: cover;
  background-position: center;

  @include media.xl-only {
    width: 100vw;
    padding: 160px 0;
    height: 100vh;
    transition: all ease-in-out .5s;

    .content-section:hover > & {
      filter: blur(4px) grayscale(100%);
    }
  }

}

.description {
  position: absolute;
  width: 100%;
  height: 40%;
  background: rgba(31, 37, 48, .87);
  bottom: 0;
  left: 0;
  padding: 20px 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  @include media.xl-only {
    padding: 30vh 30px;
    width: 30%;
    height: 100vh;
    top: 0;
    right: 0;
    transition: all ease-in-out .5s;
  }
}

.description__content {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 10px;
  @include media.xl-only {
    margin-top: 0px;
  }
}

p {
  color: var(--c-grey00);
  @include media.xl-only {
    padding: 10px 20px;
    text-align: justify;
    letter-spacing: .2rem;
    line-height: 1.6rem;
  }
}

.description__title {
  color: var(--c-primary);
  z-index: 10;
  text-align: center;
  font-size: 22px;
  margin-bottom: 20px;

  @include media.xl-only {
    font-size: 32px;
    letter-spacing: .5rem;
  }
}

.description__items {
  display: none;
  @include media.xl-only {
    opacity: 0;
    top: -10%;
    right: 0;
    position: absolute;
    width: 70%;
    height: 110vh;
    transition: all ease-in-out .3s;
    z-index: 20;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    place-items: center;
    background-color: transparent;

    @media screen and (min-width: 1667px) {
      top: -15%;
    }

    .content-section:hover > & {
      opacity: 1;
    }
  }
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
