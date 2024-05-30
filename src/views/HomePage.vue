<script>
import TheHeader from "@/components/HomePageComponents/TheHeader.vue";
import FirstPage from "@/components/HomePageComponents/FirstPage.vue";
import HorizontalBlocks from "@/components/HomePageComponents/HorizontalBlocks.vue";
import CheckBoxUsage from "@/components/HomePageComponents/CheckBoxUsage.vue";
import InformationText from "@/components/HomePageComponents/InformationText.vue";
import SliderComponent from "@/components/HomePageComponents/SliderComponent.vue";
import TheFooter from "@/components/HomePageComponents/TheFooter.vue";
export default {
  components: {
    CheckBoxUsage,
    TheHeader,
    FirstPage,
    HorizontalBlocks,
    InformationText,
    SliderComponent,
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
    <FirstPage
        content="Make your interior more
                   minimalistic & modern"
    />
    <FirstPage
        content="Turn your room with panto into a lot more
                   minimalist and modern with ease and speed" />
    <FirstPage
        content="Let's search furniture!"
        :is-last-page="true"
    />
    <HorizontalBlocks :blocks="horizontalBlocks"/>
    <CheckBoxUsage/>
    <InformationText/>
    <SliderComponent/>
    <TheFooter/>
  </div>
</template>

<style>
.parallax {
  background: url(../assets/img/background.jpg) fixed no-repeat;
  background-size: cover;
  position: relative;
  box-sizing: border-box;
}
</style>