<template>
  <li class="last-viewed-item">
    <img :src="item.picture" :alt="item.name" class="product-image" />
    
    <button class="like-button">
      <i class="far fa-heart heart-icon"></i>
    </button>

    <h3>{{ item.name }}</h3>

    <div class="rating">
      <i v-for="n in 5" :key="n" :class="n <= item.stars ? 'fas fa-star yellow' : 'far fa-star gray'"></i>
      <span class="reviews">
        <i class="fas fa-comment comment-icon"></i> 
        {{ item.reviews }}
      </span>
    </div>

    <p :class="item.isPresent ? 'available' : 'not-available'">
      {{ item.isPresent ? 'Є в наявності' : 'Немає в наявності' }}
    </p>

    <p v-if="item.oldPrice !== item.newPrice" class="old-price">{{ item.oldPrice }} ₴</p>
    <p :class="item.oldPrice === item.newPrice ? 'price' : 'discount-price'">{{ item.newPrice }} ₴</p>
  </li>
</template>

<script>
export default {
  name: "LastViewedItem",
  props: { item: Object }
};
</script>

<style scoped>
.last-viewed-item {
  position: relative;
  width: 400px;
  list-style: none;
  align-content: center;
  padding: 15px;
  background: white;
  border-radius: 8px;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  margin-bottom: 10px;
}
.product-image {
  width: 100px;
  border-radius: 8px;
}
.like-button {
  position: absolute;
  right: 18px;
  top: 18px;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
.heart-icon {
  font-size: 24px; 
  color: #ffc107; 
}
.yellow {
  color: #ffc107;
}
.gray {
  color: #b0b0b0; 
}
.available {
  color: green;
}
.not-available {
  color: red;
}
.price {
  font-size: 18px;
  font-weight: bold;
  color: black;
}
.old-price {
  font-size: 14px;
  color: grey;
  text-decoration: line-through;
}
.discount-price {
  font-size: 18px;
  font-weight: bold;
  color: red;
}

.reviews {
  margin-left: 30px;
  font-size: 14px;
  color: #666;
}

.comment-icon {
  font-size: 16px;
  margin-right: 4px;
  color: #666;
}
</style>
