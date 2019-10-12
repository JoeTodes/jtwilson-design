<template>
  <v-img :height="this.windowHeight-64" :src="src"></v-img>
</template>

<script>
export default {
  data() {
    return {
      windowHeight: 0,
      windowWidth: 0,
      src: ``,
      imgLoaded: false
    };
  },
  mounted() {
    this.windowHeight = window.innerHeight;
    this.windowWidth = window.innerWidth;
    this.src = `https://picsum.photos/${this.windowWidth}/${this.windowHeight}`;
  }
};
</script>
