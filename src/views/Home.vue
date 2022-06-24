<template>
  <div class="home flex">
    <p class="flex">hello world</p>
    <p>body</p>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  components: {},
})
export default class Home extends Vue {}
</script>
