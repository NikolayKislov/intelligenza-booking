<template>
  <nav class="nav" :class="{'nav--active': isActive}">
    <ul class="nav__list">
      <li
        v-for="item in navLinks"
        :key="item.title"
        :class="{'nav__item' : true, 'nav__item--has-child' : item.children }">
        <a class="nav__link" :href="item.link">{{ item.title }}</a>
        <ul v-if="item.children" class="nav__child-list">
          <li v-for="childItem in item.children" :key="childItem" class="nav__child-item">
            <a
              class="nav__link nav__child-link"
              :href="childItem.link"
            >{{ childItem.title }}</a>
          </li>
        </ul>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "TheNav",
  data: () => ({
    isActive: false,
    navLinks: [
      {
        title: 'ABOUT',
        link: '#about',
      },
      {
        title: 'SERVICES',
        link: '/',
        children: [
          {
            title: 'HOTELS',
            link: '#hotels'
          },
          {
            title: 'CONCERTS',
            link: '#concerts'
          },
          {
            title: 'YACHTS',
            link: '#yachts'
          },
          {
            title: 'AIRPLANES',
            link: '#planes'
          },
          {
            title: 'CARS',
            link: '#cars'
          },
        ]
      },
      {
        title: 'CONTACTS',
        link: '/'
      }
    ]
  }),
  created() {
    this.$nuxt.$on('toggle-menu', () => {
      this.isActive = !this.isActive
    })
  }
}
</script>

<style lang="scss" scoped>
@use "@/assets/styles/helpers/helpers";
@use "@/assets/styles/helpers/media";


.nav {
  position: fixed;
  top: 35px;
  left: 0;
  width: 100%;
  height: 100vh;
  background: var(--c-grey100);
  transform: translateX(-100%);
  transition: 0.3s all;

  @include media.md-to-lg {
    height: 64px;
    transform: translateX(40%);
    top: 1%;
    width: 400px;
    left: 30%;
    background: transparent;
  }

  @include media.lg-up {
    left: 45%;
    transform: translateX(40%);
    top: 1%;
    width: 400px;
    height: 64px;
  }

  @include media.xl-only {
    transform: translateX(60%);
  }

  &--active {
    transform: translateX(0%);
  }
}

.nav__list {
  display: flex;
  flex-direction: column;
  list-style: none;
  align-items: flex-start;
  padding-top: 100px;
  max-width: 200px;
  margin: 0 auto;
  gap: 20px;

  @include media.md-up {
    flex-direction: row;
    padding: 0;
    margin: 0;
    align-items: flex-end;
  }
}

.nav__item {
  padding: 20px 0 10px;
  position: relative;
}

.nav__link {
  @extend %hover-animation;
  font-size: 30px;
  text-align: start;
  letter-spacing: .3rem;
  @include media.md-up {
    font-size: 18px;
  }
}

.nav__child-list {
  display: flex;
  position: relative;
  list-style: none;
  flex-direction: column;
  gap: 15px;
  background: rgba(31, 37, 48, .3);
  padding: 20px 0px;
  text-align: start;
  min-width: 220px;

  @include media.md-up {
    display: none;
    text-align: center;
    padding: 20px 30px;
  }

  .nav__item--has-child:hover & {
    display: flex;
    margin-top: 20px;
    margin-bottom: 20px;
    padding-top: 0;
    padding-bottom: 0;

    @include media.md-up {
      position: absolute;
      bottom: 0;
      transform: translate(-26%, 100%);
      margin: 0;
      padding:20px 0;
    }
  }
}

.nav__child-link {
  padding: 20px 0 10px;
  font-size: 20px;
  color: var(--c-grey100);

  @include media.md-up {
    font-size: 15px;
  }
}
</style>
