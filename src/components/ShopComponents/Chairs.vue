<template>
  <div class="chair">
    <h1>Chairs</h1>
    <p class="p">
      <span>Versatility:</span> Many chair models are versatile and can be used in multiple settings, from dining rooms and living rooms to home offices and bedrooms, providing flexibility in decorating and furnishing.
      <br>
      <span>Sturdy Construction:</span> Chairs are built with sturdy construction methods and quality craftsmanship, ensuring stability and reliability for everyday use.
      <br>
      <span>Affordable Pricing:</span> Despite the high quality and design options, Panto Furniture offers chairs at competitive prices, making them accessible to a wide range of customers.
    </p>
    <div class="description">
      <div>
      </div>
    </div>
    <div class="card__container">
      <div v-for="(chair, index) in visibleChairs" :key="index" class="card">
        <img :src="chair.image" alt="изображение">
        <div class="card__content">
          <p class="card__name">{{ chair.name }}</p>
          <p class="card__description">{{ chair.description }}</p>
          <p class="card__price">{{ chair.price }}</p>
          <button @click="addToCart(chair)" class="add-to-cart-btn">В корзину</button>
        </div>
      </div>
    </div>
    <button v-if="!showingAll" @click="showAll">Показать все</button>
    <button v-if="showingAll" @click="showLess">Показать меньше</button>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const chairs = ref([]);
const visibleChairs = ref([]);
const showingAll = ref(false);

const fetchChairs = async () => {
  try {
    const response = await fetch('/data/chair.json');
    chairs.value = await response.json();
    visibleChairs.value = chairs.value.slice(0, 5);
  } catch (error) {
    console.error('Ошибка загрузки данных:', error);
  }
};

const showAll = () => {
  visibleChairs.value = chairs.value;
  showingAll.value = true;
};

const showLess = () => {
  visibleChairs.value = chairs.value.slice(0, 5);
  showingAll.value = false;
}

const addToCart = (chair) => {
  // Здесь можно реализовать логику добавления стула в корзину
  console.log(`Добавлено в корзину: ${chair.name}`);
};

onMounted(() => {
  fetchChairs();
});
</script>




<style>
.chair h1{
  padding-top: 30px;
  text-align: center;
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
  padding-bottom: 30px;
}
.p{
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
  text-align: center;
  line-height: 100px;
  background: rgba(30, 30, 30, 0.59);
  border: 4px solid #1E1E1E;
  width: 83%;
}
.p span{
  color: orange;
}
.card__container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;

}

.card {
  position: relative;
  width: 200px;
  height: 260px;
  background-color: rgba(242, 242, 242, 0.1);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  perspective: 1000px;
  box-shadow: 0 0 0 5px rgba(242, 242, 242, 0.1);;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.card img {
  width: 100%;
  object-fit: cover;
  fill: #333;
  transition: all 0s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.card:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px rgba(255, 255, 255, 0.2);
}

.card__content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 20px;
  box-sizing: border-box;
  background-color: rgba(242, 242, 242, 0.1);
  transform: rotateX(-90deg);
  transform-origin: bottom;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.card:hover .card__content {
  transform: rotateX(0deg);
}

.card__name{
  margin: 0;
  font-size: 24px;
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
  font-weight: 700;
}

.card:hover img {
  scale: 0;
}

button {
  display: block;
  margin: 20px auto;
  padding: 10px 20px;
  font-size: 16px;
  background-color: #333;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #555;
}
.add-to-cart-btn {
  background-color: #333;
  color: black;
  border: none;
  padding: 8px 12px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.add-to-cart-btn:hover {
  background-color: #fff;
}
</style>