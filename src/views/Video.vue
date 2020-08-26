<template>
    <div>
        <div class='container'>
            <video
            :id='videoData[0].id'
            class="video-js vjs-big-play-centered position"
            controls
            preload="auto"
            width="100%"
            height="60%"
            :poster="videoData[0].image"
            data-setup="{}"
            :key='videoData[0].id'
            >
                <source :src='videoData[0].videoLink' type="video/mp4" />
                <p class="vjs-no-js">
                To view this video please enable JavaScript, and consider upgrading to a
                web browser that
                <a href="https://videojs.com/html5-video-support/" target="_blank"
                    >supports HTML5 video</a>
                </p>
            </video>
            <div style="padding-top:15px;">
                <h1>{{videoData[0].title}}</h1>
                <h6>{{videoData[0].duration}} &bull; {{videoData[0].category}} &bull; {{dor}}</h6>
                <p>{{videoData[0].description}}</p>
                <table>
                    <tr v-for="(i, index) in videoCast" :key="index">
                        <th>
                            {{videoCast[index].role}} 
                        </th>
                        <td style="padding-left:20px;">
                            {{videoCast[index].name}}
                        </td>
                    </tr>
                </table>
            </div>
        </div>
        <image-slider/>
    </div>
</template>

<script>
import ImageSlider from '../components/ImageSlider.vue'
import axios from 'axios';
export default {
    name:'Video',
    components: {
        ImageSlider
    },
    data: function () {
        return {
            videoData: null,
            dor:null,
            videoCast:null,
            id:this.$route.params.id
        }
    },
    created() {
    },
    mounted () {
        axios.get(`https://balu-ott.herokuapp.com/video/getVideoDetails/${this.id}`)
        .then((res)=>{
            this.videoData = res.data;
            this.dor = (this.videoData[0].dor).substring(0, 4)
            console.log(this.videoData);
        })
        axios.get(`https://balu-ott.herokuapp.com/video/getVideoCast/${this.id}`)
        .then((res)=>{
            this.videoCast = res.data;
            console.log(this.videoCast);
        })
  }
}
</script>

<style scoped>
.video-js{
    width:100%;
    height: 540px;
}
.position{
    margin-top: 10px;
}
@media (min-width: 1200px){
    .container{
        max-width: 1420px;
    }
}
</style>