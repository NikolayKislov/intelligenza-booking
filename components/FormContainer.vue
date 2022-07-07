<template>
  <div class="form" id="contacts">
    <div class="container form__container">
      <div v-if="succeededSent">
        <h3 class="form__message">THANKS FOR FILLING OUR FORM!</h3>
      </div>
      <TheForm v-else/>
      <div class="form__contacts">
        <h2 class="title">CONTACT US</h2>
        <a href="mailto:noc@advancedmailsystem.com">noc@advancedmailsystem.com</a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "FormContainer",
  data: () => ({
    succeededSent: false,
    navLinks: [
      {
        title: 'Main',
        link: '/',
      },
      {
        title: 'Services',
        link: '#',
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
    this.$nuxt.$on('sent-form', () => {
      this.succeededSent = true
    })
  }
}
</script>
<style lang="scss" scoped>
@use '@/assets/styles/helpers/helpers';
@use '@/assets/styles/helpers/media';
@use '@/assets/styles/helpers/heading';
.form {
  background-color: var(--c-grey100);
  margin-top: -100px;
}

.form__container {
  padding-top: 180px;
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  justify-content: center;
  margin: 0;
  gap: 30px;
  padding-bottom: 80px;

  @include media.md-up {
    flex-direction: row;
    align-items: flex-start;
    margin: 0 auto;
    gap: 10%;
  }
}

.form__contacts {
  text-align: center;
  width: 320px;
}


a {
  @extend %hover-animation;

  @include media.md-up {
    max-width: 320px;
    font-size: 24px;
  }
  font-size: 14px;
  text-decoration: none;
  color: var(--c-grey100);
  max-width: 250px;
  text-align: center;
}

.form__message {
  min-height: 377px;
  max-width: 320px;
  color: var(--c-primary);
  font-size: 32px;
  display: flex;
  align-items: center;
  justify-items: center;
  margin: 0;
}

.title {
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
</style>
