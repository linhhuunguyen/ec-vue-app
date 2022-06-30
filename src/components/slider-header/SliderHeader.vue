<template>
  <div class="navigation flex">
    <Carousel
      :itemsToShow="9"
      :itemsToScroll="8"
      :snapAlign="right"
      ref="myCarousel"
    >
      <Slide v-for="(image, index) in images" :key="index">
        <div class="flex items-center">
          <div class="w-14 h-14">
            <img :src="image.url" />
          </div>
          <span>{{ image.name }}</span>
        </div>
      </Slide>
    </Carousel>
    <div class="flex-1 flex space-x-2 pl-6 py-[6px]">
      <button @click="myCarousel.prev()">Prev</button>
      <button @click="myCarousel.next()">next</button>
    </div>
  </div>
</template>

<script>
import { ref, onMounted, toRefs } from "vue";
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
  },
  setup() {
    const myCarousel = ref(null);

    return {
      myCarousel,
    };
  },
};
</script>

<style lang="css">
.navigation .carousel {
  width: 100%;
  overflow: hidden;
  cursor: grab;
}

.navigation .carousel__prev {
  right: 0;
  left: unset;
}

.navigation .carousel__slide {
  justify-content: flex-start;
  width: unset !important;
  padding-left: 0.25rem;
  padding-right: 0.75rem;
  border-radius: 0.5rem;
  transition: background-color 0.3s ease-in-out;
}

.carousel__prev--in-active,
.carousel__next--in-active {
  display: none;
}
</style>
