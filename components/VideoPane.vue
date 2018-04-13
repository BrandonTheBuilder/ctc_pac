<template>
    <div>
        <video v-if="videoIndex==0" key="videoZero" autoplay loop muted preload="true" width="auto" height="100%">
          <source src="img/SunnyVidWebsite.webm" type="video/webm">
        </video>
        <video v-if="videoIndex==1" key="videoOne" autoplay loop muted preload="true" width="auto" height="100%">
          <source src="img/FoggyVidWebsite.webm" type="video/webm">
        </video>
    </div>
</template>
<script>
export default {
    data: function() {
        return {
            videoIndex: 0
        }
    }
}
</script>