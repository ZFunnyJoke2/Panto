<template>
  <div class="title">
    <h1>Best selling products</h1>
    <div class="radio-inputs">
      <label>
        <input class="radio-input" type="radio" value="Chairs" v-model="selectedCategories">
        <span class="radio-tile">
					<span class="radio-icon">
            <img src="@/assets/img/chair-wooden-svgrepo-com.svg" alt="chair">
					</span>
					<span class="radio-label">Chairs</span>
				</span>
      </label>

      <label>
        <input class="radio-input" type="radio" value="Beds" v-model="selectedCategories">
        <span class="radio-tile">
					<span class="radio-icon">
            <img src="@/assets/img/bed-svgrepo-com.svg" alt="bed">
					</span>
					<span class="radio-label">Beds</span>
				</span>
      </label>

      <label>
        <input class="radio-input" type="radio" value="Sofa" v-model="selectedCategories">
        <span class="radio-tile">
					<span class="radio-icon">
            <img src="@/assets/img/sofa-free-4-svgrepo-com.svg" alt="sofa">
					</span>
					<span class="radio-label">Sofa</span>
				</span>
      </label>
    </div>
    <div v-if="selectedCategories.includes('Chairs')">
      <ul class="ul-checkbox">
        <li>
          <img src="@/assets/img/1chair.jpg" alt="chair">
          <p>Folsder chair<br> 99$</p>
        </li>
        <li>
          <img src="@/assets/img/SKANSNAS.png" alt="chair">
          <p>Skansnas chair<br> 999$</p>
        </li>
        <li>
          <img src="@/assets/img/PINNTORP.png" alt="chair">
          <p>Pinntorp chair<br> 999$</p>
        </li>
        <li>
          <img src="@/assets/img/3chair.jpg" alt="chair">
          <p>Seichlka chair<br> 139$</p>
        </li>
      </ul>
    </div>
    <div v-if="selectedCategories.includes('Beds')">
      <ul class="ul-checkbox">
        <li>
          <img src="@/assets/img/1Bed.jpg" alt="bed">
          <p>Classic bed<br> 399$</p>
        </li>
        <li>
          <img src="@/assets/img/HEMNES.png" alt="bed">
          <p>Hemnes bed<br> 299$</p>
        </li>
        <li>
          <img src="@/assets/img/LYNGОR.png" alt="bed">
          <p>Lyngor bed<br> 449$</p>
        </li>
        <li>
          <img src="@/assets/img/3Bed.jpg" alt="bed">
          <p>Comfortable<br> 459$</p>
        </li>
      </ul>
    </div>
    <div v-if="selectedCategories.includes('Sofa')">
      <ul class="ul-checkbox">
        <li>
          <img src="@/assets/img/GLOSTAD.png" alt="sofa">
          <p>Glostad sofa<br> 499$</p>
        </li>
        <li>
          <img src="@/assets/img/FRIDHULT.png" alt="sofa">
          <p>Fridhult sofa<br> 399$</p>
        </li>
        <li>
          <img src="@/assets/img/HOLMSUND.png" alt="sofa">
          <p>Holmsund sofa<br> 299$</p>
        </li>
        <li>
          <img src="@/assets/img/VIMLE.png" alt="sofa">
          <p>Vimle sofa<br> 399$</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedCategories: ['Chairs']
    }
  }
}
</script>

<style>
.title{
  width: 100%;
  padding-top: 100px;
  text-align: center;
}
.title h1{
  padding-bottom: 30px;
  color: orange;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
}
.ul-checkbox{
  display: flex;
  align-items: center;
  justify-content: space-between;
  list-style: none;
  padding-top: 50px;
}
.ul-checkbox p{
  font-size: 1.2rem;
  font-weight: bold;
  background-image: url("@/assets/img/FirstPageTextBackground.png");
  color: #333;
  border: 2px solid #333;
  border-radius: 10px;
}
.ul-checkbox li img{
  width: 200px;
  height: 200px;
  border: 2px solid #333;
  border-radius: 10px;
  padding: 10px;
}
.radio-inputs {
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 350px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  margin-left: 665px;
}

.radio-inputs > * {
  margin: 6px;
}

.radio-input:checked + .radio-tile {
  border-color: #333;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  color: #333;
}

.radio-input:checked + .radio-tile:before {
  transform: scale(1);
  opacity: 1;
  background-color: #333;
  border-color: #333;
}

.radio-input:checked + .radio-tile .radio-label {
  color: #333;
}

.radio-input:focus + .radio-tile {
  border-color: #333;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1), 0 0 0 4px #333;
}

.radio-input:focus + .radio-tile:before {
  transform: scale(1);
  opacity: 1;
}

.radio-tile {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 80px;
  min-height: 80px;
  border-radius: 0.5rem;
  border: 2px solid #333;
  background-color: #fff;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  transition: 0.15s ease;
  cursor: pointer;
  position: relative;
}

.radio-tile:before {
  content: "";
  position: absolute;
  display: block;
  width: 0.75rem;
  height: 0.75rem;
  border: 2px solid #b5bfd9;
  background-color: #fff;
  border-radius: 50%;
  top: 0.25rem;
  left: 0.25rem;
  opacity: 0;
  transform: scale(0);
  transition: 0.25s ease;
}

.radio-tile:hover {
  border-color: #333;
}

.radio-tile:hover:before {
  transform: scale(1);
  opacity: 1;
}

.radio-icon svg {
  width: 2rem;
  height: 2rem;
  fill: #494949;
}

.radio-label {
  color: #707070;
  transition: 0.375s ease;
  text-align: center;
  font-size: 13px;
}

.radio-input {
  clip: rect(0 0 0 0);
  -webkit-clip-path: inset(100%);
  clip-path: inset(100%);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}
.radio-icon img{
  width: 2rem;
}

</style>
