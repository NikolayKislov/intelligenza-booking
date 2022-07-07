<template>
  <div>
    <TheHeader/>
    <PageHero
      title="INTELLEGENZA"
      subtitle="As far as you need good partner at your dream trip, we’re on your service"
      image="hero-bg.jpg"
    />
    <SectionAbout id="about"/>
    <AdvantagesSection/>
    <ContentSection
      id="hotels"
      path="hotels"
      file="hotels-bg.jpg"
      title="HOTELS BOOKING"
      :description-items="descriptionItemsHotels"
      :image-items="imageItemsHotels"
    />
    <ContentSection
      id="concerts"
      path="concerts"
      file="concerts-bg.jpg"
      title="TICKETS BOOKING"
      :description-items="descriptionItemsConcerts"
      :image-items="imageItemsConcerts"
    />
    <ContentSection
      id="yachts"
      path="yachts-booking"
      file="yachts-bg.jpg"
      title="YACHTS RENT"
      :description-items="descriptionItemsYachts"
      :image-items="imageItemsYachts"
    />
    <ContentSection
      id="planes"
      path="plane-booking"
      file="plane-bg.jpg"
      title="PLANE RENT"
      :description-items="descriptionItemsPlanes"
      :image-items="imageItemsPlanes"
    />
    <ContentSection
      id="cars"
      path="car-booking"
      file="car-bg.jpg"
      title="CAR RENT"
      :description-items="descriptionItemsCars"
      :image-items="imageItemsCars"
    />
    <FormContainer
    id="contacts"
    />
    <TheFooter />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      imageItemsHotels: ['hotels-1.jpg', 'hotels-4.jpg', 'hotels-3.jpg', 'hotels-2.jpg'],
      descriptionItemsHotels: ['We offer free booking of hotels, resorts with a search in our system.',
        'Here you will find detailed information on how to rent a hotel online, the location of the hotel, directions, prices, etc.',
        'At your service, hotels of different classes: elite and chain hotels, mini-hotels, budget places and cottages.'
      ],
      imageItemsConcerts: ['concerts-3.jpg', 'concerts-4.jpg', 'concerts-1.jpg', 'concerts-2.jpg'],
      descriptionItemsConcerts: ['Our platform provides  a ticketing service where organisers sell tickets to their guests directly without the involvement of an intermediary.',
        'Including ticket sellers can be official distributors of the event.',
        'This means that the buyer receives direct contact with the person responsible for the successful organisation and provision of services for the event.'
      ],
      imageItemsYachts: ['yacht-3.jpg', 'yacht-2.jpg', 'yacht-1.jpg', 'yacht-4.jpg'],
      descriptionItemsYachts: ['Get a free list of available charter boats for you. Yachts, sailboats, inflatable boats, motor boats, catamarans - everything is at your service!',
        'Charter for whoever you want, when you want. We will cover the costs associated with its maintenance and use.',
        'You will also receive comprehensive insurance for up to 8 million euros.'
      ],
      imageItemsPlanes: ['plane-3.jpg', 'plane-2.jpg', 'plane-1.jpg', 'plane-4.jpg'],
      descriptionItemsPlanes: ['We love to provide the safest and most modern aircraft with the best cabin equipment.',
        'We only have modern and well-equipped aircraft ready to fly all over the world. You can rent an aircraft for days, weeks or even months and return it at your destination. ',
        'Choose from over a hundred aircraft the one you like and enjoy.'
      ],
      imageItemsCars: ['car-1.jpg', 'car-3.jpg', 'car-2.jpg', 'car-4.jpg'],
      descriptionItemsCars: ['We  started out  10 years ago with a fleet of just six vehicles. Now we are one of the first and most influential international car rental companies in the world. We have earned a trusted reputation from our clients.',
        'Today we are present in all over the world! You will be able to easily find our car rental services internationally. ',
        'You will find exact what you need!'
      ]

    }
  }
}
</script>
<style lang="scss">
@use '@/assets/styles/helpers/grid';
@use '@/assets/styles/helpers/media';
@use '@/assets/styles/helpers/helpers';

body {
  scroll-behavior: smooth;
}

</style>
