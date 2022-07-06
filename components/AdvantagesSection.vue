<template>
  <section class="advantages">
    <div class="container advantages__container">
      <AdvantagesItem
        v-for="item in advantagesItems"
        :key="`${item.title}`"
        :image="`${item.image}`"
        :title="`${item.title}`"
        :description="`${item.description}`"
      />
    </div>
  </section>
</template>

<script>
export default {
  name: 'AdvantagesSection',
  data() {
    return {
      advantagesItems: [
        {
          image: '10.png',
          title: 'More than 10 years on the market!',
          description: 'We have been growing and developing for ten years now!'
        },
        {
          image: 'thumbs-up.png',
          title: '9 out of 10 clients recommend us!',
          description: 'We have an excellent customer-oriented service 24/7!'
        },
        {
          image: 'one-million.png',
          title: 'One million of happy customers!',
          description : 'Just try once, and you will fall in love!'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.advantages__container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 65px;
  flex-wrap: wrap;
  margin-bottom: 150px;
}
</style>
