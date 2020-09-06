<template>
    <carousel 
        :nav= "false"
        :dots= "false"
        :responsive="{
          0:{
            items: 1
          },
          600:{
            items: 3
          },
          1000:{
            items: 4
          },
          1200:{
            items: 5
          }
        }"
    >
        <template slot="prev">
          <img src="https://img.icons8.com/metro/40/000000/long-arrow-left.png"/>
        </template>
        <div class="item">
          1  
        </div>
        <div class="item">
          2 
        </div>
        <div class="item">
          3 
        </div>
        <div class="item">
          4 
        </div>
        <div class="item">
          5
        </div>
        <div class="item">
          6 
        </div>
        <div class="item">
          7  
        </div>
        <div class="item">
          3 
        </div>
        <div class="item">
          4 
        </div>
        <div class="item">
          5
        </div>
        <div class="item">
          6 
        </div>
        <div class="item">
          7  
        </div>
        <template slot="next">
          <img src="https://img.icons8.com/metro/40/000000/long-arrow-right.png"/>
        </template>
    </carousel>
</template>

<script>
import carousel from 'vue-owl-carousel'
export default {
    components: { carousel },
    data(){
      return{
      }
    }
}
</script>

<style scoped>
 .prev{
   height: 200px;
    background: green;
    width: 2%;
    position: absolute;
    left: 0;
 }

 .next{
   height: 200px;
    background: green;
    width: 2%;
    position: absolute;
    right: 0;
 }

 .item{
   margin: 3px;
   height: 170px;
   width: 98%;
   background-color: aqua;
   color: white;
   justify-content: center;
   align-items: center;
 }
 .owl-carousel.owl-loaded {
    display: flex;
    width: 96%;
    left: 2%;
 }
 .owl-carousel .owl-stage-outer {
    width: 96%;
    margin-left: 27px;
}
 
</style>