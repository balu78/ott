<template>
  <div class="home">
    <Carousel/>
    <image-slider/>
  </div>
</template>

<script>
// @ is an alias to /src
import Carousel from '../components/Carousel.vue'
import ImageSlider from '../components/ImageSlider.vue'

export default {
  name: 'Home',
  components: {
    Carousel,
    ImageSlider
  },
}
</script>
