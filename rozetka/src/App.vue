<template>
  <div>
    <comparison-list :items="comparisonItems" />
    <last-viewed-list :items="lastViewedItems" />
  </div>
</template>

<script>
import ComparisonList from "./components/ComparisonList.vue";
import LastViewedList from "./components/LastViewedList.vue";

const comparisonItems = [
  {
    picture: "https://content1.rozetka.com.ua/goods/images/big/507062959.jpg",
    id: 1,
  },
  {
    picture: "https://content1.rozetka.com.ua/goods/images/big/221214139.jpg",
    id: 2,
  },
  {
    picture: "https://content.rozetka.com.ua/goods/images/big/417133239.jpg",
    id: 3,
  },
];

const lastViewedItems = [
  {
    id: 1,
    picture: "https://content1.rozetka.com.ua/goods/images/big/449730711.jpg",
    name: "Навушники Samsung Galaxy Buds3 Pro Silver (SM-R630NZAASEK)",
    isPresent: true,
    stars: 4,
    reviews: 69,
    oldPrice: 9599,
    newPrice: 9599,
  },
  {
    id: 2,
    picture: "https://content.rozetka.com.ua/goods/images/big/449499662.jpg",
    name: "Смарт-годинник Samsung Galaxy Watch Ultra",
    stars: 5,
    reviews: 8,
    isPresent: true,
    oldPrice: 28999,
    newPrice: 24499,
  },
  {
    id: 3,
    picture: "https://content2.rozetka.com.ua/goods/images/big/478644857.jpg",
    name: "Гантель вінілова Stein 1 кг Жовта (DB3012-1yellow)",
    stars: 5,
    reviews: 8,
    isPresent: false,
    oldPrice: 180,
    newPrice: 180,
  },
];
export default {
  name: "App",
  components: {
    ComparisonList,
    LastViewedList,
  },
  data() {
    return {
      comparisonItems: [...comparisonItems],
      lastViewedItems: [...lastViewedItems],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
