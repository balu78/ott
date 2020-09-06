<template>
    <div class="carousel-wrap">
    <div class="owl-carousel owl-theme">
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=1" />
          <span class="img-text">nightlife</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=2" />
          <span class="img-text">abstract</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=3" />
          <span class="img-text">animals</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=4" />
          <span class="img-text">nature</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=5" />
          <span class="img-text">business</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=6" />
          <span class="img-text">cats</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=7" />
          <span class="img-text">city</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=8" />
          <span class="img-text">food</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=9" />
          <span class="img-text">fashion</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=10" />
          <span class="img-text">people</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=11" />
          <span class="img-text">sports</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=12" />
          <span class="img-text">technics</span>
        </div>
        <div class="item">
          <img src="https://picsum.photos/640/480?pic=13" />
          <span class="img-text">transport</span>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'VideoSlider',

}
</script>

<style scoped>
 .carousel-wrap {
    width: 1000px;
    margin: auto;
    position: relative;
  }
  .owl-carousel .owl-nav{
    overflow: hidden;
    height: 0px;
  }

  .owl-theme .owl-dots .owl-dot.active span, 
  .owl-theme .owl-dots .owl-dot:hover span {
      background: #2caae1;
  }


  .owl-carousel .item {
      text-align: center;
  }
  .owl-carousel .nav-btn{
      height: 47px;
      position: absolute;
      width: 26px;
      cursor: pointer;
      top: 100px !important;
  }

  .owl-carousel .owl-prev.disabled,
  .owl-carousel .owl-next.disabled{
    pointer-events: none;
    opacity: 0.2;
  }

  .owl-carousel .prev-slide{
      background: url(nav-icon.png) no-repeat scroll 0 0;
      left: -33px;
  }
  .owl-carousel .next-slide{
      background: url(nav-icon.png) no-repeat scroll -24px 0px;
      right: -33px;
  }
  .owl-carousel .prev-slide:hover{
     background-position: 0px -53px;
  }
  .owl-carousel .next-slide:hover{
    background-position: -24px -53px;
  }

  span.img-text {
    text-decoration: none;
    outline: none;
    transition: all 0.4s ease;
    -webkit-transition: all 0.4s ease;
    -moz-transition: all 0.4s ease;
    -o-transition: all 0.4s ease;
    cursor: pointer;
    width: 100%;
    font-size: 23px;
    display: block;
    text-transform: capitalize;
  }
  span.img-text:hover {
    color: #2caae1;
  }
</style>