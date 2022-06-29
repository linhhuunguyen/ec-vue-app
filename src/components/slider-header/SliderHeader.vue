<template>
  <Carousel :itemsToShow="7" :snapAlign="right">
      <Slide v-for="(image, index) in images" :key="index">
      <div class="flex items-center">
        <div class="w-14 h-14">
          <img :src="image.url" />
        </div>
        <span>{{image.name}}</span>
      </div>
       
      </Slide>
    <template #addons>
      <Navigation />
    </template>
  </Carousel>
</template>

<script>
import { ref, onMounted,toRefs } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

export default {
  name: "SliderHeader",
  props: {
    images: Array,
  },
  components: {
    Carousel,
    Slide,
    Navigation,
  },
};
</script>

<style>
.carousel__prev{
  right: 0;
  left: unset;
}
</style>