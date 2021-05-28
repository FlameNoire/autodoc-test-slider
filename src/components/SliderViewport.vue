<template>
  <div class="autodoc-slider__viewport">
    <slide
      v-for="slide in slides"
      :key="slide.id"
      :img="slide.img"
      :link="slide.url"
      :linkText="slide.linkText"
      :text="slide.text"
      :title="slide.title"
      :accentTitle="slide.accentTitle"
    />
  </div>
</template>

<script>
  import Slide from './Slide.vue'

  export default {
    name: 'slider-viewport',
    components: {
      Slide
    },
    props: {
      slides: Array
    }
  }
</script>

<style lang="scss">
  .autodoc-slider__viewport {
    position: relative;
    width: 100%;
    height: 90vh;
    border: 1px solid #333;
  }
</style>