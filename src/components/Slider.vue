<template>
  <div class="autodoc-slider">
    <slider-viewport :slides="slides"/>
    <slider-panel :buttons="buttonTexts" />
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
      slides: Array
    },
    data: () => {
      return {}
    },
    computed: {
      buttonTexts: function() {
        return this.slides.map(item => item.buttonTitle)
      }
    }
  }
</script>

<style lang="scss">
  .autodoc-slider {
    position: relative;
    width: 100%;
  }
</style>