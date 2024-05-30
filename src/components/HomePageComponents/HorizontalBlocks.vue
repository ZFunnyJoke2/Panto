<script>
export default {
  name: 'HorizontalBlocks',
  props: {
    blocks: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <div class="horizontal-blocks">
    <div class="block" v-for="(block, index) in blocks" :key="index">
      <h3>{{ block.title }}</h3>
      <p>{{ block.content }}</p>
    </div>
  </div>
</template>

<style>
.horizontal-blocks {
  display: flex;
  justify-content: space-between;
  margin: 5rem auto;
  max-width: 1400px;
  background: #333;
}

.block {
  flex: 1;
  margin: 0.5rem;
  padding: 1rem;
  border: 3px solid #333;
  border-radius: 10px;
  background-color: #f9f9f9;
  text-align: left;
}
.block:first-child {
  max-width: 300px;
  flex: none;
  font-size: 30px;
}
.block:first-child h3{
  font-weight: bold;
  font-size: 2rem;
}
.block:first-child p{
  font-weight: 600;
  font-size: 1.5rem;
}
.block h3 {
  margin: 0 0 0.5rem 0;
  font-size: 1.2rem;
  font-weight: 800;
}

.block p {
  margin: 0;
  font-size: 1rem;
  font-weight: 500;
}
</style>