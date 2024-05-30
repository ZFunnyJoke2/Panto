<template>
  <div class="container">
    <section class="experience">
      <div class="content">
        <img src="@/assets/img/info-main-sofa.png" alt="Living Room" class="experience-image" />
        <div class="experience-text">
          <h2>We Provide You The<br> Best Experience</h2>
          <p>
            You don't have to worry about the result because all of<br>
            these interiors are made by people who are professionals<br>
            in their fields, with an elegant and luxurious style and<br>
            with premium quality materials.
          </p>
          <button @click="toggleText">More info</button>
          <div v-show="showText" class="text">Lorem ipsum dolor sit amet, consectetur adipiscing elit,<br>
            sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</div>
        </div>
      </div>
    </section>

    <section class="materials">
      <div class="content">
        <h2>Very Serious Materials<br> For Making Furniture</h2>
        <p>
          Because panto was very serious about designing furniture<br>
          for our environment, using a very expensive and famous<br>
          capital but at a relatively low price
        </p>
        <div class="material-images">
          <img src="@/assets/img/info-chair.png" alt="chair"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showText: false
    }
  },
  methods: {
    toggleText() {
      this.showText = !this.showText;
    }
  }
}
</script>

<style scoped>
.container {
  max-width: 1920px;
  margin: 0 auto;
  padding-top: 150px;
}

.content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: center;
}
.content h2{
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
  font-size: 3rem;
}
.content p{
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
  font-size: 1.5rem;
}
.experience,
.materials {
  margin-bottom: 40px;
}

.experience-text,
.materials h2,
.materials p {
  margin-bottom: 20px;
}
.experience-text h2{
  color: orange;
}
.content h2{
  color: orange;
}
.experience-image,
.material-images img {
  width: 100%;
  max-width: 400px;
  height: auto;
  margin-bottom: 20px;
}

.experience h2,
.materials h2 {
  font-size: 32px;
  font-weight: bold;
}

.experience p,
.materials p,
.text {
  font-size: 18px;
  line-height: 1.6;
}

button {
  padding: 10px 20px;
  background-color: rgba(250, 159, 4, 0.85);
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: rgba(250, 250, 250, 0.85);
}

.text {
  color: #888;
}


</style>
