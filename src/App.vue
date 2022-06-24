<template>
  <Header />
  <router-view />
  <Footer />
</template>

<script>
import { Options, Vue } from "vue-class-component";

// import Header from "@/layouts/Header.vue";

import Header from "@/layouts/Header.vue";
import Footer from "@/layouts/Footer.vue";

@Options({
  components: { Header, Footer },
})
export default class App extends Vue {}
</script>

<style lang="scss"></style>
