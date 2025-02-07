<template>
  <section class="last-viewed-section">
    <h2>Останні переглянуті товари</h2>
    <ul class="last-viewed-list">
      <last-viewed-item v-for="item in items" :key="item.id" :item="item" />
    </ul>
  </section>
</template>

<script>
import LastViewedItem from './LastViewedItem.vue';
export default {
  name: "LastViewedList",
  components: { LastViewedItem },
  props: { items: Array }
};
</script>

<style scoped>
.last-viewed-section {
  padding: 20px;
  background: #f5f5f5;
  border-radius: 8px;
}
.last-viewed-list {
    margin-top: 64px;
    display: flex;
    justify-content: center;
    gap: 48px;
}
</style>