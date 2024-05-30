<template>
  <div class="slider">
    <h1>Our Client Reviews</h1>
    <div class="slides" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
      <div v-for="(slide, index) in slides" :key="index" class="slide">
        <p>{{ slide.text }}</p>
      </div>
    </div>
    <button @click="prevSlide" class="nav-button prev-button">&lt;</button>
    <button @click="nextSlide" class="nav-button next-button">&gt;</button>
  </div>
</template>

<script>
import slides from '../../../public/data/slider.json';

export default {
  name: 'SliderComponent',
  data() {
    return {
      slides,
      currentSlide: 0
    };
  },
  methods: {
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.slides.length;
    },
    prevSlide() {
      this.currentSlide = (this.currentSlide - 1 + this.slides.length) % this.slides.length;
    }
  }
};
</script>

<style>
.slider {
  padding-top: 100px;
  position: relative;
  overflow: hidden;
  width: 100%;
  max-width: 1000px;
  margin: auto;
}
.slider h1 {
  text-align: center;
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
}
.slides {
  display: flex;
  align-items: center;
  width: 100%;
  transition: transform 0.5s ease-in-out;
}
.slide {
  min-width: 100%;
  box-sizing: border-box;
  text-align: center;
  justify-content: center;
  align-items: center;
  padding: 20px;
  display: flex;
  justify-content: center;
}

.slide p {
  max-width: 60%;
  margin: auto;
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
}

.nav-button {
  position: absolute;
  top: 60%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
}

.prev-button {
  left: 10px;
}

.next-button {
  right: 10px;
}
</style>
