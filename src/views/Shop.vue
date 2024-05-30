<script>
  import TheHeader from "@/components/AllUsageComponents/TheHeader.vue";
  import Chairs from "@/components/ShopComponents/Chairs.vue";
  import Beds from "@/components/ShopComponents/Beds.vue";
  import Sofa from "@/components/ShopComponents/Sofa.vue"
  import TheFooter from "@/components/AllUsageComponents/TheFooter.vue";
  export default {
    components:{
      TheFooter,
      TheHeader,
      Chairs,
      Beds,
      Sofa
    }
  }
</script>

<template>
  <div class="parallax">
    <TheHeader/>
    <div class="shop_products">
      <Chairs/>
      <Beds/>
      <Sofa/>
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

</style>