<template>
  <!-- <swiper class="swiper" :options="swiperOption">
    <swiper-slide :key="banner" v-for="banner in banners">
      <img :src="banner" alt='pic'>
    </swiper-slide>
    <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>
  </swiper> -->
  <div>
    <carousel>
    <slide>
      Slide 1 Content
    </slide>
    <slide>
      Slide 2 Content
    </slide>
    <slide>
      Slide 1 Content
    </slide>
    <slide>
      Slide 2 Content
    </slide>
  </carousel>
  </div>
</template>

<script>
  // import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
  // import '../assets/swiper/swiper-bundle.css'

  export default {
    name: 'swiper-example-navigation',
    title: 'Navigation',
    // components: {
    //   Swiper,
    //   SwiperSlide
    // },
    data() {
      return {
        banners: [ 'https://picsum.photos/id/237/200/300', 
        'https://picsum.photos/id/230/200/300',
        'https://picsum.photos/id/231/200/300',
        'https://picsum.photos/id/232/200/300',
        'https://picsum.photos/id/233/200/300',
        'https://picsum.photos/id/234/200/300',
        'https://picsum.photos/id/235/200/300',
        'https://picsum.photos/id/236/200/300',
        'https://picsum.photos/id/237/200/300',
        'https://picsum.photos/id/238/200/300',
        'https://picsum.photos/id/239/200/300',
        'https://picsum.photos/id/240/200/300',
        'https://picsum.photos/id/241/200/300',
        'https://picsum.photos/id/230/200/300',
        'https://picsum.photos/id/231/200/300',
        'https://picsum.photos/id/232/200/300',
        'https://picsum.photos/id/233/200/300',
        'https://picsum.photos/id/234/200/300',
        'https://picsum.photos/id/235/200/300',
        'https://picsum.photos/id/236/200/300',
        'https://picsum.photos/id/237/200/300',
        'https://picsum.photos/id/238/200/300',
        'https://picsum.photos/id/239/200/300',
        'https://picsum.photos/id/240/200/300',
        'https://picsum.photos/id/241/200/300',
        ],
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
            clickable: true,
          },
          nextButton: '.swiper-button-next',
          prevButton: '.swiper-button-prev',
          slidesPerView: 7,
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
          },
          observer: true,  
          observeParents: true,
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '../assets/swiper/base.scss';
</style>