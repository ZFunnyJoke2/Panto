<template>
  <section class="text-block">
    <p style="">{{ content }}</p>
    <form v-if="isLastPage" @submit.prevent="search">
      <input type="text" v-model="searchQuery" placeholder="Search furniture">
      <button class="search-btn" type="submit">
        <img src="" alt="SearchBtn"/>
      </button>
    </form>
  </section>
</template>

<script>
export default {
  name: 'FirstPage',
  props: {
    content: {
      type: String,
      required: true
    },
    isLastPage: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      searchQuery: ''
    };
  },
  methods: {
    search() {
      alert('Поиск: ' + this.searchQuery);
      this.searchQuery = '';
    }
  }
}
</script>

<style>
.text-block {
  margin: 1rem 0;
  padding: 60px;
  border: 3px solid #333;
  border-radius: 10px;
  background-color: #f9f9f9;
  max-width: 500px;
}

.text-block p {
  margin: 0.2rem 0;
  font-size: 35px;
  font-weight: bold;
}

.text-block form {
  margin-top: 1rem;
  display: flex;
}

.text-block input[type="text"] {
  flex: 1;
  padding: 0.5rem;
}

.search-btn{
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
}
</style>