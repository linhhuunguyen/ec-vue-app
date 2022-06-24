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
            v-model:value="value"
            placeholder="input search text"
            style="width: 200px"
          />
        </div>
      </div>

      <div class="ml-10 flex">
        <div>cart</div>
        <div>Shipping</div>
        <div>Notification</div>
        <div>Account</div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from "vue";
import { Options, Vue } from "vue-class-component";

import MenuIcon from "../assets/icons/menu-icon.vue";

@Options({
  components: { MenuIcon },
})
export default class Header extends Vue {}
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
