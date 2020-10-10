<template>
  <header class="container">
    <div class="info">
      <div class="info__item" v-for="item in info" :key="item.id">
        <div class="info__icon">
          <img :src="`/assets/img/${item.icon}.svg`" :alt="item.name">
        </div>
        <div class="info__title">
          {{ item.name }}
        </div>
      </div>
    </div>
  </header>
</template>

<script>
  export default {
    data() {
      return {
        info: [
          { id: 1, name: 'Возможность получать доход выше, чем по вкладу', icon: 'icon-1' },
          { id: 2, name: 'Фиксированный срок инвестирования', icon: 'icon-2' },
          { id: 3, name: 'Получите +13% к инвестициям ежегодно', icon: 'icon-3' },
          { id: 4, name: 'Все инвестиции онлайн в одном приложении', icon: 'icon-4' }
        ]
      }
    }
  }
</script>
