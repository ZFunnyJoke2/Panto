<template>
  <div id="sofa">
    <h1>Main Sofas</h1>
    <div class="card__container">
      <div v-for="(sofa, index) in visibleSofas" :key="index" class="card">
        <div class="card__content">
          <p class="card__name">{{ sofa.name }}</p>
          <p class="card__description">{{ sofa.description }}</p>
          <p class="card__price">{{ sofa.price }}</p>
          <button @click="addToCart(sofa)" class="add-to-cart-btn">В корзину</button>
        </div>
      </div>
    </div>
    <button v-if="!showingAll" @click="showAll">Показать все</button>
    <button v-if="showingAll" @click="showLess">Показать меньше</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import sofasData from '@/components/data/sofa.json';

const sofas = ref(sofasData);
const visibleSofas = ref(sofas.value.slice(0, 5));
const showingAll = ref(false);

const showAll = () => {
  visibleSofas.value = sofas.value;
  showingAll.value = true;
};

const showLess = () => {
  visibleSofas.value = sofas.value.slice(0, 5);
  showingAll.value = false;
};

const addToCart = (sofa) => {
  // Здесь можно реализовать логику добавления дивана в корзину
  console.log(`Добавлено в корзину: ${sofa.name}`);
};
</script>

<style>
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
  color: #c82222;
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
