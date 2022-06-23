<template>
  <div class="about">
    <div v-show="isShow"><h1>This is an about page</h1></div>
    <button @click="isShow = !isShow">show/off</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: true,
    };
  },
};
</script>
