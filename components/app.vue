<template>
<section> 
    <video-pane ref="video"/>  
    <div>
        <img class="logoimage" src="img/CTCPAC_LOGO.png">
    </div>
    <ul class="nav" id="navMenu">
        <li class="navMenuItem" id="aboutMenuItem" 
        v-on:click="aboutPage">
            <a>About</a>
        </li>
        <li class="navMenuItem" id="aoiMenuItem" v-on:click="aoiPage">
            <a>Areas of Interest</a>
        </li>
    </ul> 
    <content-pane ref="contents"/>
</section>
</template>
<script>
import Vue from 'vue'
import ContentPane from './ContentPane.vue'
import VideoPane from './VideoPane.vue'
Vue.component('content-pane', ContentPane) 
Vue.component('video-pane', VideoPane)
export default{
    data: function() {
        return {

        }
    },
    methods: {
        aboutPage: function(event) {
            this.$refs.contents.currentPage="about";
            this.$refs.video.videoIndex=0;
        },
        aoiPage: function(event) {
            this.$refs.contents.currentPage="aoi";
            this.$refs.video.videoIndex=1;
        }
    }
    
}
</script>

<style>
    
</style>