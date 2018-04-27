<template>
    <app class="app"/>
</template>

<script>
import app from '~/components/app.vue'

export default {
  components: {
    'app': app
  }
}
</script>

<style>
.app{
    overflow: hidden;
    position: relative;
}
</style>
