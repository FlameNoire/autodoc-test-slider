<template>
  <div class="autodoc-slider">
    <slider-viewport
      :options="options"
      :slides="slides"
      :activeIndex="activeSlide"
    />
    <slider-panel
      :options="options"
      :buttons="buttonTexts"
      :activeIndex="activeSlide"
      @slideChange="slideChange"
      @mouseOver="mouseOver"
      @mouseLeave="mouseLeave"
    />
  </div>
</template>

<script>
  import SliderViewport from './SliderViewport.vue'
  import SliderPanel from './SliderPanel.vue'

  export default {
    name: 'slider',
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
        pause: false
      }
    },
    computed: {
      activeSlide: function() {
        return  this.activeIndex
      },
      buttonTexts: function() {
        return this.slides.map(item => item.buttonTitle)
      },
      isPause: function () {
        return this.pause
      }
    },
    methods: {
      slideChange(index) {
        this.activeIndex = index
      },
      slideAutoChange() {
        this.intervalID = setInterval(() => {
          this.activeIndex < this.slides.length - 1 ? this.activeIndex++ : this.activeIndex = 0
        }, 5000)
      },
      mouseOver() {
        this.pause = true
        clearInterval(this.intervalID)
      },
      mouseLeave() {
        this.pause = false
        this.slideAutoChange()
      },
    },
    mounted() {
      this.activeIndex = this.options.activeSlide - 1
      this.slideAutoChange()
      console.log(this)
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