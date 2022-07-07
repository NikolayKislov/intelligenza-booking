<template>
  <div class="form" id="contacts">
    <form class="form__submit-form">
      <input type="text" id="fname" name="fname" placeholder="NAME">
      <input type="text" id="mail" name="mail" placeholder="MAIL">
      <textarea placeholder="YOUR MESSAGE"></textarea>
      <p>By using this form you agree with the storage and handling of you data by this website.</p>
      <button class="btn form__btn" @click="submitAction($event)">Submit</button>
    </form>
  </div>
</template>
<script>
export default {
  name: 'TheForm',
  methods: {
    submitAction(event) {
      event.preventDefault()
      this.$nuxt.$emit('sent-form')
    },
  },
}
</script>
<style lang="scss" scoped>
@use '@/assets/styles/helpers/media';

.form__submit-form {
  padding-top: 80px;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 20px;
  min-width: 320px;

  @include media.md-up {
    align-items: flex-start;
  }
}

input {
  min-width: 310px;
  height: 52px;
  padding: 5px 15px;
  background-color: var(--c-grey100);
  border: none;
  box-shadow: 1px 1px 1px rgba(84, 179, 214, 1);
  color: var(--c-grey00);

  &:focus {
    outline: 2px solid var(--c-primary);
  }

}

p {
  color: var(--c-primary);
  width: 310px;
  height: 52px;
  line-height: 1.5;
  margin: 0;
  padding: 0;
}

textarea {
  min-width: 310px;
  height: 150px;
  padding: 5px 15px;
  resize: none;
  background-color: var(--c-grey100);
  border: none;
  box-shadow: 1px 1px 1px rgba(84, 179, 214, 1);
  color: var(--c-grey00);

  &:focus {
    outline: 2px solid var(--c-primary);
  }
}

.form__btn {
  border: none;
}
</style>
