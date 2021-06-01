<template>
  <div class="autodoc-slider__panel">
    <SliderButton
      v-for="(button, index) in buttons"
      :key="index"
      :text="button"
      :slideNum="index + 1"
      :buttonWidth=buttonWidth
      :class="{'active' : index === activeSlide}"
      :isProgress="options.autoplay"
      :progressStatus="index === activeSlide"
      :progressDuration="options.slideChangeTime"
      @slideChangeHandler="slideChangeHandler"
      @mouseoverHandler="mouseoverHandler"
      @mouseleaveHandler="mouseleaveHandler"
    />
  </div>
</template>

<script>
  import SliderButton from './SliderButton.vue'

  export default {
    name: 'slider-panel',
    props: {
      options: Object,
      activeIndex: Number,
      buttons: Array,
    },
    components: {
      SliderButton
    },
    computed: {
      activeSlide: function () {
        return this.activeIndex
      },
      buttonWidth: function () {
        return 100 / this.buttons.length
      }
    },
    methods: {
      slideChangeHandler(index) {
        this.$emit('slideChange', index - 1)
      },
      mouseoverHandler(pause) {
        this.$emit('mouseOver', pause)
      },
      mouseleaveHandler(pause) {
        this.$emit('mouseLeave', pause)
      },
    }
  }

</script>

<style lang="scss">
  .autodoc-slider__panel {
    width: 100%;
    height: 8vh;
    display: flex;
    align-items: stretch;
  }
</style>