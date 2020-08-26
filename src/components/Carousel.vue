<template>
  <div>
    <b-carousel class="carousel "
      id="carousel-1"
      v-model="slide"
      :interval="2000"
      controls
      indicators
      background="#ababab"
      img-width="1024px"
      img-height="200px"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        img-src="https://i1.wp.com/www.socialnews.xyz/wp-content/uploads/2020/01/09/Mahesh-Babu-and-Rashmika-Mandanna-s-Cute-Poster-from-Sarileru-Neekevvaru-movie-.jpg?resize=2048%2C964&quality=90&zoom=1&ssl=1"
        class="carousel"
      ></b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide img-src="https://in.bmscdn.com/iedb/movies/images/mobile/listing/xxlarge/ala-vaikunthapuramulo-et00109721-15-08-2019-01-57-15.jpg" class="carousel">
      <h1>asdf</h1>
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
  export default {
    name: 'Carousel',
    components: {  },
    data() {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart() {
        this.sliding = true
      },
      onSlideEnd() {
        this.sliding = false
      }
    }
  }
</script>


<style scoped>
.carousel {
  height: 400px;
}
.img-fluid {
  height: -webkit-fill-available;
}
</style>