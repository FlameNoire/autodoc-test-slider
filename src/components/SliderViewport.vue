<template>
  <div class="autodoc-slider__viewport">
    <transition-group name="fade">
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
    </transition-group>
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
  }
</script>

<style lang="scss">
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 1.5s;
  }
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
  .autodoc-slider__viewport {
    position: relative;
    width: 100%;
    height: 90vh;
  }
</style>