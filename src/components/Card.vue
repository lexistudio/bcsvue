<template>
  <section class="container">
    <h2 class="title card-title">Лучшие готовые инвестиционные решения</h2>
    <Tab v-on:filters="addFilter" />
    <Slider :filters="filter" />
  </section>
</template>

<script>
import Tab from '@/components/Tab.vue'
import Slider from '@/components/Slider.vue'

  export default {
    components: {
      Tab,
      Slider
    },
    data() {
      return {
        filter: ''
      }
    },
    methods: {
      addFilter(arg) {
        this.filter = arg
      }
    }
  }

</script>
