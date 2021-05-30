<template>
  <div class="autodoc-slider">
    <slider-viewport :options="options" :slides="slides" :activeIndex="activeSlide" />
    <slider-panel :buttons="buttonTexts" @slideChange="slideChange" :activeIndex="activeSlide" />
  </div>
</template>

<script>
  import SliderViewport from './SliderViewport.vue'
  import SliderPanel from './SliderPanel.vue'

  export default {
    name: 'autodoc-slider',
    components: {
      SliderViewport,
      SliderPanel
    },
    props: {
      options: Object,
      slides: Array
    },
    data: () => {
      return {
        activeIndex: 0,
      }
    },
    computed: {
      activeSlide: function() {
        return  this.activeIndex
      },
      buttonTexts: function() {
        return this.slides.map(item => item.buttonTitle)
      }
    },
    methods: {
      slideChange(index) {
        this.activeIndex = index
      }
    }
  }
</script>

<style lang="scss">
  .autodoc-slider {
    position: relative;
    width: 100%;
    color: #3C4247;
  }
</style>