<template>
  <div class="autodoc-slider__viewport">
    <slide
      v-for="(slide, index) in slides"
      v-show="index === activeSlide"
      :key="slide.id"
      :class="{'active' : index === activeSlide}"
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
      options: Object,
      slides: Array,
      activeIndex: Number
    },
    computed: {
      activeSlide: function () {
        return this.activeIndex
      }
    },
    methods: {
      slideChange() {}
    }
  }
</script>

<style lang="scss">
  .autodoc-slider__viewport {
    position: relative;
    width: 100%;
    height: 90vh;
  }
</style>