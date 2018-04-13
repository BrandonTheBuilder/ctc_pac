<template>
<section class="ctc"> 
    <video-pane ref="video" class="videoPane"></video-pane>  
    <div class="logo">
        <img class="logoimage" src="img/CTCPAC_LOGO.png">
    </div>
    <div class="navMenuWrapper">    
        <ul class="nav" id="navMenu">
            <li class="navMenuItem" id="aboutMenuItem" 
            v-on:click="aboutPage">
                <a class="menuText">About</a>
            </li>
            <li class="navMenuItem" id="aoiMenuItem" v-on:click="aoiPage">
                <a class="menuText">Areas of Interest</a>
            </li>
        </ul> 
    </div>
    <content-pane ref="contents" class="contents"></content-pane>
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
.ctc{
    position: relative;
    display: block;
    overflow: hidden;
}

.nav{
    list-style-type: none;
    width: 696px;
    text-align: center;
}

.navMenuWrapper{
    position: absolute;
    top: 0;
    left: 0;
    display: table;
    margin: 0 auto;
    text-align: center; 
}

.navMenuItem{
    text-decoration: none;
    display: inline;
    padding-left: 25px;
}
.menuText{
    font-size: 26px;
    font-family: PSFournierWebBold;
    text-align: center;
}
.logo{
    z-index: 1;
    position: absolute;
    left: 10%;
    top: 5%;
    width: 200px;
}
.contents{
    text-align: center;
    position: absolute;
    top: 50px;
    right: 0;
}

.videoPane{
    /*position: absolute;*/
    /*top: 0;*/
    /*left: 0;*/
    overflow: hidden; 
}

.videoPane::-webkit-scrollbar {
  display: none !important;
}

</style>