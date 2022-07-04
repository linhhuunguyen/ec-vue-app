<template>
  <div class="navigation flex container mx-auto py-4">
    <Carousel
      :itemsToShow="10"
      :itemsToScroll="10"
      :snapAlign="right"
      ref="myCarousel"
    >
      <Slide v-for="(image, index) in images" :key="index">
        <div class="flex items-center">
          <div class="w-14 h-14">
            <img :src="image.url" />
          </div>
          <span class="flex-1 whitespace-nowrap text-xs font-bold">{{
            image.name
          }}</span>
        </div>
      </Slide>
    </Carousel>
    <div class="flex-1 flex items-center space-x-2 pl-6 py-[6px]">
      <button
        @click="onPrev"
        id="prev"
        disabled
        class="flex items-center justify-center w-10 h-10 arrow-btn disabled:opacity-25"
      >
        <ArrowLeftIcon />
      </button>
      <button
        @click="onNext"
        id="next"
        class="flex items-center justify-center w-10 h-10 arrow-btn disabled:opacity-25"
      >
        <ArrowRightIcon />
      </button>
    </div>
  </div>
</template>

<script>
import { ref, onMounted, toRefs } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";
import ArrowRightIcon from "@/assets/icons/arrow-right-icon.vue";
import ArrowLeftIcon from "@/assets/icons/arrow-left-icon.vue";

import "vue3-carousel/dist/carousel.css";

export default {
  name: "SliderHeader",
  props: {
    images: Array,
  },
  components: {
    Carousel,
    Slide,
    ArrowRightIcon,
    ArrowLeftIcon,
  },
  setup() {
    const myCarousel = ref(null);

    const getSlideCount = ref(null);
    const lii = document.getElementsByClassName("carousel__slide");
    const onNext = () => {
      if (
        lii[lii.length - 11].className ===
        "carousel__slide carousel__slide--visible"
      ) {
        const nextbtn = document.getElementById("next");
        nextbtn.setAttribute("disabled", true);
      }

      const prevbtn = document.getElementById("prev");
      prevbtn.removeAttribute("disabled");
      myCarousel.value.next();
    };

    const onPrev = () => {
      const nextbtn = document.getElementById("next");
      nextbtn.removeAttribute("disabled");
      if (lii[11].className === "carousel__slide carousel__slide--visible") {
        const prevbtn = document.getElementById("prev");
        prevbtn.setAttribute("disabled", true);
      }
      myCarousel.value.prev();
    };

    onMounted(() => {
      getSlideCount.value = document.getElementsByClassName(".carousel__slide");

      console.log("liii");
    });

    return {
      myCarousel,
      onNext,
      onPrev,
      getSlideCount,
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
  /* width: unset !important; */
  padding-left: 0.25rem;
  padding-right: 0.75rem;
  border-radius: 0.5rem;
  transition: background-color 0.3s ease-in-out;

  --tw-bg-opacity: 1;
  background-color: rgba(235, 243, 255, var(--tw-bg-opacity));
}

.arrow-btn {
  --tw-bg-opacity: 1;
  background-color: rgba(248, 250, 252, var(--tw-bg-opacity));
  border-radius: 50%;
}

.arrow-btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.carousel__prev--in-active,
.carousel__next--in-active {
  display: none;
}
</style>
