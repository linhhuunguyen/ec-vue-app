<template>
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
        <div class="ml-5">
          <a-input-search
            class="hello"
            v-model:value="value"
            placeholder="input search text"
            style="width: 200px"
            @change="onSearch"
          />
        </div>
      </div>

      <div class="ml-10 flex">
        <div class="flex mx-5">
          <CardIcon />
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
</template>

<script lang="ts">
import MenuIcon from "../assets/icons/menu-icon.vue";
import CardIcon from "../assets/icons/card-icon.vue";
import ShippingIcon from "../assets/icons/shipping-icon.vue";
import NotificationIcon from "../assets/icons/notification-icon.vue";
import UserIcon from "../assets/icons/user-icon.vue";

export default {
  name: "Header",
  components: { MenuIcon, CardIcon, ShippingIcon, NotificationIcon, UserIcon },
  data() {
    return {
      value: "linkkkkk",
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
<style>
.container {
  width: 100%;
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
