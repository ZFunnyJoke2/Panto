<template>
  <section class="text-block">
      <div class="card-wrapper">
        <div class="card">
          <p style="">{{ content }}</p>
      </div>
    </div>
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
}
</script>

<style scoped>

.card-wrapper {
  padding-top: 30px;
  margin-left: -800px;
}

.card {
  color: rgba(255, 255, 255, 0);
  border-radius: 10px;
  filter: drop-shadow(0 5px 10px #ffffff);
  width: 700px;
  height: 180px;
  font-size: 20px;
  padding: 20px;
  position: relative;
  z-index: 0;
  overflow: hidden;
  transition: 0.6s ease-in;
}

.card::before {
  content: "";
  position: absolute;
  z-index: -1;
  top: -15px;
  right: -15px;
  background: #333;
  height:220px;
  width: 25px;
  border-radius: 32px;
  transform: scale(1);
  transform-origin: 50% 50%;
  transition: transform 0.25s ease-out;
}

.card:hover::before{
  transition-delay:0.2s ;
  transform: scale(60);
}

.card:hover{
  color: #ffffff;
}

.card p{
  padding: 10px 0;
}
</style>