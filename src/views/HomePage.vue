<script>
import TheHeader from "@/components/AllUsageComponents/TheHeader.vue";
import FirstPage from "@/components/HomePageComponents/FirstPage.vue";
import HorizontalBlocks from "@/components/HomePageComponents/HorizontalBlocks.vue";
import CheckBoxUsage from "@/components/HomePageComponents/CheckBoxUsage.vue";
import InformationText from "@/components/HomePageComponents/InformationText.vue";
import TheFooter from "@/components/AllUsageComponents/TheFooter.vue";
export default {
  components: {
    CheckBoxUsage,
    TheHeader,
    FirstPage,
    HorizontalBlocks,
    InformationText,
    TheFooter
  },
  data() {
    return {
      horizontalBlocks: [
        { title: 'Why', content: 'Choosing us' },
        { title: 'Luxury facilities', content: 'The advantage of hiring a workspace with us is that givees you comfortable service and all-around facilities.' },
        { title: 'Affordable Price', content: 'You can get a workspace of the highst quality at an affordable price and still enjoy the facilities that are oly here.' },
        { title: 'Many Choices', content: 'We provide many unique work space choices so that you can choose the workspace to your liking.' }
      ]
    }
  }
}
</script>

<template>
  <div class="parallax">
    <TheHeader/>
    <div class="shadow">
      <FirstPage
          content="Welcome to the world of style and comfort with Panto furniture store!

Panto is your reliable partner in creating the coziness and functionality of your home. We offer a wide range of high-quality furniture for every room: from the living room to the bedroom, from the kitchen to the office."
      />
      <FirstPage
          content="Our mission is to help you turn your home into a space that reflects your style and meets your needs. We take pride in our innovative designs, high level of quality, and affordable prices.

Immerse yourself in the world of comfort and beauty with Panto today! Visit our store or shop online for convenience and time-saving." />
      <FirstPage
          content="Trust us with the care of your home, and you'll discover how space can become a source of inspiration and joy.

Make your home - perfect with Panto!"
      />
      <HorizontalBlocks :blocks="horizontalBlocks"/>
      <CheckBoxUsage/>
      <InformationText/>
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
  height: 2800px;
}
</style>