<script>
import TheHeader from "@/components/AllUsageComponents/TheHeader.vue";
import TheFooter from "@/components/AllUsageComponents/TheFooter.vue";
import Contacts from "@/components/ContactComponents/Contacts.vue";
import SliderComponent from "@/components/ContactComponents/SliderComponent.vue";

  export default {
    components: {
      TheHeader,
      TheFooter,
      Contacts,
      SliderComponent
    }
  }
</script>

<template>
  <div class="parallax">
    <TheHeader/>
    <div class="shadow">
      <Contacts/>
      <SliderComponent/>
    </div>
    <TheFooter/>
  </div>
</template>

<style scoped>
.parallax {
  background: url(../assets/img/background.jpg) fixed no-repeat;
  background-size: cover;
  position: relative;
  box-sizing: border-box;
}
.shadow{
  width: 90%;
  background: rgba(18, 17, 17, 0.66);
  height: 1700px;
}
</style>