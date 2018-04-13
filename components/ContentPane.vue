<template>
<transition name="component-fade" mode="out-in">
    <component v-bind:is="currentPage"></component>
</transition>
</template>
<script>
import AboutPage from './AboutPage.vue'
import AoiPage from './AoiPage.vue'

export default{
    data: function() {
        return {
            currentPage: 'about'
        }
    },
    components: {
        'about': AboutPage,
        'aoi': AoiPage
    }
}
</script>
<style>
.component-fade-enter-active, .component-fade-leave-active {
  transition: opacity 0s ease;
}
.component-fade-enter, .component-fade-leave-to
/* .component-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
