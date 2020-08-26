<template>
    <div>
        <div class="background">
            <div class="carousel">
            <div @click="previous()" class="carousel__control carousel__control--previous">
                <i class="fa fa-arrow-left"></i>
            </div>
            <ul>
                <li v-for="item in videoData" :key="item.id" @click="methodThatForcesUpdate()" class="carousel__item">
                    <router-link  :to="{ name:'video', params:{id:item.id}}" :key="item.id">
                        <img :src="item.image"/>
                    </router-link>
                </li>
            </ul>
            <div @click="next()" class="carousel__control carousel__control--next">
                <i class="fa fa-arrow-right"></i>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Carousel',
  data: function () {
    return {
      videoData: null
    }
  },
  methods: {
    next: function () {
      this.videoData.push(this.videoData.shift())
    },
    previous: function () {
      this.videoData.unshift(this.videoData.pop())
    },
    methodThatForcesUpdate() {
      console.log("reload");
      location.reload();
    }
  },
  mounted () {
    axios.get('https://balu-ott.herokuapp.com/video/getVideo')
      .then((res)=>{
          this.videoData = res.data;
          console.log(this.videoData)
      })
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