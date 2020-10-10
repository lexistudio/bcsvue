<template>
  <div class="tab">
    <div
      class="tab__item"
      v-for="item in tab"
      :key="item.id"
      v-on:click="addFilter(item.filter)"
      :class="{ active: filter == item.filter }"
    >
      {{ item.name }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tab: [
        { id: 1, name: "Гарантированная доходность", filter: "one" },
        { id: 2, name: "Регулярная доходность", filter: "two" },
        { id: 3, name: "Ставка на рост", filter: "three" },
      ],
      filter: "",
    };
  },
  methods: {
    addFilter(arg) {
      this.filter = arg
      this.$emit('filters', arg)
    }
  }
};
</script>
