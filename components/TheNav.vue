<template>
  <nav class="nav" :class="{'nav--active': isActive}">
    <ul class="nav__list">
      <li :class="{'nav__item' : true, 'nav__item--has-child' : item.children }" v-for="item in navLinks">
        <nuxt-link class="nav__link" :to="item.link">{{ item.title }}</nuxt-link>
        <ul class="nav__child-list" v-if="item.children">
          <li class="nav__child-item" v-for="childItem in item.children">
            <a class="nav__link nav__child-link" :href="childItem.link">{{ childItem.title }}</a>
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
        title: 'Main',
        link: '/',
      },
      {
        title: 'Services',
        link: '/',
        children: [
          {
            title: 'Data centers',
            link: '/data-center'
          },
          {
            title: 'Smart yachts',
            link: '/smart-yachts'
          },
          {
            title: 'Cyber security ',
            link: '/cyber-security'
          },
        ]
      },
      {
        title: 'Contacts',
        link: '/contacts'
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
@use "../assets/styles/helpers/helpers";
@use "../assets/styles/helpers/media";


.nav {
  position: fixed;
  top: 35px;
  left: 0;
  width: 100%;
  height: 100vh;
  background: var(--c-grey00);
  transform: translateX(-100%);
  transition: 0.3s all;

  @include media.md-to-lg {
    height: 65px;
    transform: translateX(80%);
    top: 1%;
    width: 400px;
    left: 30%;
  }

  @include media.lg-up {
    left: 45%;
    transform: translateX(80%);
    top: 1%;
    width: 400px;
    height: 65px;
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
  background: var(--c-grey00);
  padding: 20px 0px;
  text-align: start;
  min-width: 220px;

  @include media.md-up {
    display: none;
    text-align: center;
    padding: 20px 30px;
  }

  .nav__item--has-child:hover & {
    @extend %box-shadow;
    display: flex;

    @include media.md-up {
      position: absolute;
      border-radius: var(--b-radius);
      bottom: 0;
      transform: translate(-30%, 100%);
    }
  }
}

.nav__child-link {
  font-size: 20px;
  color: var(--c-grey100);

  @include media.md-up {
    font-size: 15px;
  }
}
</style>
