<template>
  <li class="comparison-item">
    <img :src="item.picture" alt="Product" class="product-image" />
  </li>
</template>

<script>
export default {
  name: "ComparisonItem",
    props: { item: Object }
};
</script>

<style scoped>
.comparison-item {
  list-style: none;
  padding: 24px;
}
.product-image {
  width: 200px;
  border-radius: 8px;
}
</style>