<template>
<section class="ctc"> 
    <content-pane ref="contents" class="contents"
        v-bind:style="{width: pageWidth}"></content-pane>
    <video-pane ref="video" class="videoPane" 
        v-bind:style="{width: videoWidth}"></video-pane>  
    <div class="logo">
        <img class="logoimage" src="img/CTCPAC_LOGO.png" width=64px height=64px v-on:click="showHome">
    </div>
    <div class="navMenuWrapper" v-bind:style="{left: menuPosition}">   
        <ul class="nav" id="navMenu" 
                v-bind:style="{color: menuColor}">
            <li class="navMenuItem" id="aboutMenuItem" 
            v-on:click="aboutPage">
                <a class="menuText">About</a>
            </li>
            <li class="navMenuItem" id="aoiMenuItem" v-on:click="aoiPage">
                <a class="menuText">Areas of Interest</a>
            </li>
            <li class="navMenuItem" id="donateMenuItem" v-on:click="donatePage">
                <a class="menuText">Donate</a>
            </li>
        </ul> 
    </div>
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
            showingHome : true,
            videoWidth: '100%',
            pageWidth: '0%',
            menuPosition: '0%',
            menuColor: 'white'
        }
    },
    methods: {
        aboutPage: function(event) {
            this.$refs.contents.currentPage="about";
            this.$refs.video.videoIndex=0;
            if (this.showingHome) {this.showingHome = false;}
            this.setPageSize();
        },
        aoiPage: function(event) {
            this.$refs.contents.currentPage="aoi";
            this.$refs.video.videoIndex=1;
            if (this.showingHome) {this.showingHome = false;}
            this.setPageSize();
        },
        donatePage: function(event) {
            this.$refs.contents.currentPage="donate";
            this.$refs.video.videoIndex=2;
            if (this.showingHome) {this.showingHome = false;}
            this.setPageSize();
        },
        showHome: function(event) {
            if (!this.showingHome) {this.showingHome = true;}
            this.setPageSize();
        },
        setPageSize(){
            if (this.showingHome) {
                this.videoWidth = '100%';
                this.pageWidth = '0%';
                this.menuPosition = '0%';
                this.menuColor = 'white';
            }
            if (!this.showingHome) {
                this.videoWidth = '60%';
                this.pageWidth = '40%';
                this.menuPosition = 'calc(100% - 750px)';
                this.menuColor = 'black';
            }
            this.$refs.video.setVideoMargin();
        }
    }
    
}
</script>

<style>
.ctc{
    display: block;
    overflow: hidden;
    position: relative;
    height: 100%;
    width: 100%;
}

.nav{
    list-style-type: none;
    width: 696px;
    text-align: center;
    transition: color 2.0s ease 0.0s;
}

.navMenuWrapper{
    position: absolute;
    top: 0%;
    left: 0%;
    display: table;
    margin: 0 auto;
    text-align: center; 
    overflow: hidden;
    transition: left 2.0s ease 0.0s;
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
    transition: width 2.0s ease 0.0s;
    text-align: center;
    position: absolute;
    top: 5%;
    right: 0%;
    overflow: hidden;
    height: 100%;
}

.videoPane{
    overflow: hidden; 
    text-align: center;
    transition: width 2.0s ease 0.0s;
    height: 100vh;
}

.videoPane::-webkit-scrollbar {
  display: none !important;
}

</style>