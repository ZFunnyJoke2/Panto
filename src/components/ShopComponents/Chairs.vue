<template>
  <div id="chair">
    <h1>Chairs</h1>
    <div class="description">
      <div>
        <p>  The Sopranos is a crime drama TV series created by David Chase, and
          widely recognized as one of the greatest series of all time.

          It follows protagonist Tony Soprano (James Gandolfini), a New Jersey
          -based Italian-American mob boss, who struggles to manage his family and
          criminal life. Suffering from panic attacks, Tony attends therapy sessions
          with psychiatrist Jennifer Melfi (Lorraine Bracco), whom he confides in.

          Throughout the six seasons of the series, Tony has to contend with his
          uncle, Junior (Dominic Chianese); his wife, Carmela (Edie Falco); and
          threats from mobsters both within the family and external, such as the
          New York City-based Lupertazzi family.

          A prequel film to The Sopranos has been confirmed. Titled The Many Saints
          of Newark, it centers on the 1967
          Newark riots and will feature a young Tony Soprano (Michael Gandolfini),
          among other characters. The film was
          released on September 24, 2021.</p>
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
import { ref } from 'vue';
import chairsData from '@/components/data/chair.json';

const chairs = ref(chairsData);
const visibleChairs = ref(chairs.value.slice(0, 5));
const showingAll = ref(false);

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
</script>


<style scoped>
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