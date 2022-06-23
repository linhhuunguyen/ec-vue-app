<template>
  <div class="home">
    <HelloWorld msg="Hương Lii" />
    <Header />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import Header from "@/layouts/Header.vue";

@Options({
  components: {
    HelloWorld,
    Header,
  },
})
export default class Home extends Vue {}
</script>
