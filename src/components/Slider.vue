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
        pause: false,
        progress: 0
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
      },
      progressStatus: function () {
        return this.progress
      },
      autoPlay: function () {
        return this.options.autoplay
      }
    },
    methods: {
      slideChange(index) {
        this.activeIndex = index
        clearInterval(this.intervalID)
        this.slideAutoChange()
      },
      slideAutoChange() {
        if ( this.autoPlay && !this.isPause ) {
          this.intervalID = setInterval(() => {
            this.activeIndex < this.slides.length - 1 ? this.activeIndex++ : this.activeIndex = 0
          }, this.options.slideChangeTime)
        }
      },
      mouseOver(pause) {
        this.pause = pause
        clearInterval(this.intervalID)
      },
      mouseLeave(pause) {
        this.pause = pause
        clearInterval(this.intervalID)
        this.slideAutoChange()
      },
    },
    mounted() {
      this.activeIndex = this.options.startSlide <= this.slides.length ? this.options.startSlide - 1 : 0
      if ( this.autoPlay ) {
        this.slideAutoChange()
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