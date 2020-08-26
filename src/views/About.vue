<template>
  <div class="background">
    <div class="carousel">
      <div @click="previous()" class="carousel__control carousel__control--previous">
        <i class="fa fa-arrow-left"></i>
      </div>
      <ul>
        <li v-for="item in items" :key="item" class="carousel__item">
          <img :src="item"/>
        </li>
      </ul>
      <div @click="next()" class="carousel__control carousel__control--next">
        <i class="fa fa-arrow-right"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
  data: function () {
    return {
      items: [
        'https://picsum.photos/500/301', 
        'https://picsum.photos/500/300',
        'https://picsum.photos/500/300?random',
        'https://picsum.photos/510/300?random',
        'https://picsum.photos/500/301', 
        'https://picsum.photos/500/300',
        'https://picsum.photos/500/300?random',
        'https://picsum.photos/510/300?random',
        'https://picsum.photos/500/301', 
        'https://picsum.photos/500/300',
        'https://picsum.photos/500/300?random',
        'https://picsum.photos/510/300?random',
        'https://picsum.photos/500/301', 
        'https://picsum.photos/500/300',
        'https://picsum.photos/500/300?random',
        'https://picsum.photos/510/300?random',
        'https://picsum.photos/500/301', 
        'https://picsum.photos/500/300',
        'https://picsum.photos/500/300?random',
        'https://picsum.photos/510/300?random',
      ]
    }
  },
  methods: {
    next: function () {
      this.items.push(this.items.shift())
    },
    previous: function () {
      this.items.unshift(this.items.pop())
    }
  }
}
</script>

<style lang="scss" scoped>
$amount-items--desktop: 5;
$amount-items--tablet: 3;
$amount-items--mobile: 2; 
 
// colors
$background-color: #ffffff;
$hover-color: #0000006e;
$color: #ffffff;

// responsive mixins
@mixin tablet {
  @media (min-width: 768px) {
    @content;
  }
}
@mixin desktop {
  @media (min-width: 1024px) {
    @content;
  }
}
.background {
  display: flex;
  align-self: center;
}
.carousel {
  margin-top: 10px;
  width: 100%;
  height: 12em;
  display: flex;
  color: $color;
  
  &__control {
    display: flex;
    width: 100%;
    background-color: $background-color;
    align-items: center;
    justify-content: center;
    
    &:hover {
      cursor: pointer;
      background-color: $hover-color;
    }
  }
  
  & ul {
    display: flex;
    width: 98%;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  &__item {
    width: 20%;
    & img {
      height: 100%;
      border-radius: 10%;
      padding:2px;
      width: 282px;
      &:hover{
        transform: scale(1.2);
        z-index: 1;
        transition: .5s ease;
      }
    }
  }
}
</style>