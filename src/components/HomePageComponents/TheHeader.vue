<script>
export default {
  name: 'TheHeader',
  data() {
    return {
      showDropdown: false
    };
  },
  methods: {
    toggleDropdown() {
      this.showDropdown = !this.showDropdown;
    },
    handleClickOutside(event) {
      const header = this.$el;
      if (!header.contains(event.target)) {
        this.showDropdown = false;
      }
    },
    scrollToBottom(id,align){
      let el = document.getElementById(id);
      el.scrollIntoView({behavior:'smooth',block:align})
    }
  },
  mounted() {
    document.addEventListener('click', this.handleClickOutside);
  },
  beforeUnmount() {
    document.removeEventListener('click', this.handleClickOutside);
  }
}
</script>

<template>
  <header class="header">
    <div class="container">
      <router-link to="/" class="home">Panto</router-link>
      <nav class="nav">
        <ul>
          <li @click.stop="toggleDropdown">
            <a href="#" class="dropdown-link">Furniture</a>
            <span :class="{'arrow': true, 'open': showDropdown}" class="dropdown-container"></span>
            <ul v-if="showDropdown" class="dropdown">
              <li><router-link to="/shop" @click="scrollToBottom('chair','start')">Chair</router-link></li>
              <li><router-link to="/shop" @click="scrollToBottom('beds','middle')">Beds</router-link></li>
              <li><router-link to="/shop" @click="scrollToBottom('sofa','end')">Sofa</router-link></li>
            </ul>
          </li>
          <li><router-link to="/shop">Shop</router-link></li>
          <li><a href="#">About us</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
      <div class="cart">
        <img src="" alt="Bag"/>
      </div>
    </div>
  </header>

</template>

<style>
*{
  font-family: Gilroy-Light, sans-serif;
}
.header {
  background-color: #333;
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
  padding: 1rem 0;
}
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}
.home{
  font-size: 1.5rem;
  text-decoration: none;
  color: #f9f9f9;
}
.home:hover{
  color: #333333;
}
.nav ul {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
}
.nav li {
  position: relative;
  margin-left: 1rem;
}
.nav a {
  color: #fff;
  text-decoration: none;
}
.nav a:hover {
  text-decoration: underline;
}
.dropdown-container {
  display: flex;
  align-items: center;
}
.dropdown-link {
  display: inline-flex;
  align-items: center;
  flex-direction: column;
}
.arrow {
  margin-left: 0.5rem;
  width: 0;
  height: 0;
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: 5px solid #fff;
  transition: transform 0.3s ease;
}
.arrow.open {
  transform: rotate(180deg);
}
.dropdown {
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #444;
  list-style: none;
  margin: 0;
  padding: 0.5rem 0;
  display: block;
}
.dropdown li {
  margin: 0;
}
.dropdown a {
  padding: 0.5rem 1rem;
  display: block;
  white-space: nowrap;
}
.dropdown a:hover {
  background-color: #555;
}
</style>