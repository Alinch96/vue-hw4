<template>
    <section class="comparison-section">
        <h2 class="title">Списки порівнянь</h2>
        <h3>Мобільні телефони</h3>
        <p>Кількість товарів: {{ items.length }}</p>
        <ul class="comparison-list">
            <comparison-item v-for="item in items" :key="item.id" :item="item" />
        </ul>
    </section>
</template>

<script>
import ComparisonItem from "./ComparisonItem.vue";
export default {
    name: "ComparisonList",
    components: { ComparisonItem },
    props: { items: Array },
};
</script>

<style scoped>
.comparison-section {
    padding: 20px;
    background: #f8f8f8;
    border-radius: 8px;
}
.title {
    margin-bottom: 64px;
}

.comparison-list {
    margin-top: 64px;
    display: flex;
    justify-content: center;
    align-items: baseline;
}


</style>
