<template>
  <div class="header">
    <div class="container mx-auto py-4">
      <div class="flex items-center">
        <div class="flex-1 flex items-center">
          <div class="logo">
            <img src="../assets/logo.png" alt="logo" class="w-32" />
          </div>
          <div class="ml-5 flex">
            <div class="flex items-center">
              <button>
                <MenuIcon />
              </button>
              <span class="ml-2">Menu</span>
            </div>
            <div class="ml-2">Sale</div>
          </div>
          <div class="ml-5 w-full">
            <a-input-search
              class="search-input"
              v-model:value="value"
              placeholder="input search text"
              style="width: 200px"
              @change="onSearch"
            />
          </div>
        </div>

        <div class="ml-10 flex">
          <div class="flex mx-5">
            <CardIcon class="mr-2" />
            <span>0</span>
          </div>
          <div class="mx-5">
            <ShippingIcon />
          </div>
          <div class="mx-5">
            <NotificationIcon />
          </div>
          <div class="ml-5">
            <UserIcon />
          </div>
        </div>
      </div>
    </div>
  </div>
  <SliderHeader :images="carouselSlides" />
</template>

<script lang="ts">
import MenuIcon from "@/assets/icons/menu-icon.vue";
import CardIcon from "@/assets/icons/card-icon.vue";
import ShippingIcon from "@/assets/icons/shipping-icon.vue";
import NotificationIcon from "@/assets/icons/notification-icon.vue";
import UserIcon from "@/assets/icons/user-icon.vue";
import SliderHeader from "@/components/slider-header/SliderHeader.vue";
import { Menu } from "@/components/slider-header/countant";

export default {
  name: "Header",
  components: {
    SliderHeader,
    MenuIcon,
    CardIcon,
    ShippingIcon,
    NotificationIcon,
    UserIcon,
  },
  data() {
    return {
      value: "",
      carouselSlides: Menu,
    };
  },
  methods: {
    onSearch(event: Event) {
      const { value } = event.target as HTMLInputElement;
      console.log("value", value);
    },
  },
};
</script>
<style lang="css">
.header {
  --tw-bg-opacity: 1;
  background-color: rgba(255, 255, 255, var(--tw-bg-opacity));
  border-bottom-width: 1px;
  --tw-border-opacity: 1;
  border-color: rgba(236, 240, 244, var(--tw-border-opacity));
  height: var(--t-header);
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  z-index: 101;
}

.container {
  width: 100%;
}

.search-input {
  width: 100% !important;
}

@media (min-width: 1280px) {
  .container {
    max-width: 1280px;
  }
}
@media (min-width: 1024px) {
  .container {
    max-width: 1024px;
  }
}
@media (min-width: 768px) {
  .container {
    max-width: 768px;
  }
}
@media (min-width: 640px) {
  .container {
    max-width: 640px;
  }
}
</style>
