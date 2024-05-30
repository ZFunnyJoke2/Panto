<template>
  <div id="Info">
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
          <button>More info</button>
          <div class="text">Lorem ipsum dolor sit amet, consectetur adipiscing elit,<br>
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
        <button id="showText">More info</button>
        <div id="Text">Lorem ipsum dolor sit amet, consectetur adipiscing elit,<br>
          sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</div>
        <div class="material-images">
          <img src="@/assets/img/info-chair.png" alt="chair"/>
          <img src="@/assets/img/info-sofa.png" alt="sofa"/>
          <img src="@/assets/img/info-chairs.png" alt="chair"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return{
      name: 'InformationText'
    }
  }
}
</script>

<style>
.experience .content {
  display: flex;
  align-items: center; /* Центрирование по вертикали */
  justify-content: space-between; /* Распределение пространства между элементами */
}
.experience .experience-image {
  max-width: 50%; /* Устанавливает максимальную ширину изображения */
  height: auto; /* Сохраняет пропорции изображения */
}
.experience .experience-text {
  max-width: 50%; /* Устанавливает максимальную ширину текста */
  padding: 20px; /* Отступы вокруг текста */
}
.materials .content {
  display: flex;
  align-items: flex-start; /* Выравнивание по верхнему краю */
  justify-content: space-between; /* Распределение пространства между текстом и изображениями */
}

.materials .material-images {
  display: flex;
  flex-direction: column; /* Вертикальное расположение изображений */
  align-items: flex-end; /* Выравнивание изображений по правому краю */
  max-width: 50%; /* Ограничение ширины блока с изображениями */
}

.materials .material-images img {
  max-width: 100%; /* Обеспечение адаптивности изображений */
  height: auto; /* Сохранение пропорций изображений */
}

.materials .material-images .bottom-images img {
  width: 48%; /* Устанавливает ширину нижних изображений */
}
</style>
