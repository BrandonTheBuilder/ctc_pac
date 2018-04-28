<template>
    <div ref="videoPane">
        <video ref="video" v-if="videoIndex==0" key="videoZero" autoplay loop muted preload="true" width="auto" height="auto"
        v-bind:style="{left: videoLeft, top: videoTop}">
          <source src="img/SunnyVidWebsite.webm" type="video/webm">
        </video>
        <video v-if="videoIndex==1" key="videoOne" autoplay loop muted preload="true" width="auto" height="auto"
         v-bind:style="{left: videoLeft, top: videoTop}">
          <source src="img/FoggyVidWebsite.webm" type="video/webm">
        </video>
        <video v-if="videoIndex==2" key="videoTwo" autoplay loop muted preload="true" width="auto" height="auto"
         v-bind:style="{left: videoLeft, top: videoTop}">
          <source src="img/SunnyVidWebsite.webm" type="video/webm">
        </video>
    </div>
</template>
<script>
export default {
    data: function() {
        return {
            videoIndex: 0,
            margin: 'auto',
            videoLeft: 0,
            videoTop: 0,
            videoShowing: true
        }
    },
    methods: {
        setVideoMargin: function(event) {
            var videoHeight = this.$refs.video.clientHeight;
            var videoWidth = this.$refs.video.clientWidth;
            var paneHeight = this.$refs.videoPane.clientHeight;
            var paneWidth = this.$refs.videoPane.clientWidth;
            var videoTop = -(videoHeight - paneHeight)/2;
            var videoLeft = -(videoWidth - paneWidth)/2;
            
            this.videoTop = videoTop + 'px';
            this.videoLeft = videoLeft + 'px';
        }
    },
    mounted() {
        window.addEventListener('resize', this.setVideoMargin);
        this.setVideoMargin();
    }
}
</script>
<style>
video {
    height: auto;
    width: auto;
    position: relative;
    margin: auto;
}
</style>