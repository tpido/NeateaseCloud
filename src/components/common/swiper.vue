<template>
  <div id="swiper">
    <swiper ref="mySwiper" :options="swiperOptions" autoplay>
      <slot></slot>
    </swiper>
    <div class="111">111</div>
    <div class="swiper-button-next swiper-button-white"></div>
  </div>
</template>

<script>
import { swiper, swiperSlide } from "vue-awesome-swiper";
import "swiper/dist/css/swiper.css";
export default {
  name: "",
  data() {
    return {
      swiperOptions: {
        autoplay: true, // 自动轮播
        speed: 1000, // 轮播速度
        slidesPerView: 5,
        spaceBetween: 30,
        nextButton: ".111",
        prevButton: "",
        pagination: {
          el: ".swiper-pagination",
        },
        on: {},
        // Some Swiper option/callback...
      },
    };
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper;
    },
  },
};
</script>
<style scoped>
#swiper {
  overflow: hidden;
  width: 100%;
}

.red {
  background-color: red;
}

img {
  width: 100%;
}
</style>