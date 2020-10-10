<template>
  <div id="app">
    <Info />
    <Card />
  </div>
</template>

<script>
import Info from '@/components/Info.vue'
import Card from '@/components/Card.vue'

export default {
  name: 'App',
  components: {
    Info,
    Card
  }
}
</script>

<style lang="stylus">
  @import './css/site.styl'
</style>
