<template>
  <div class="autodoc-slider__panel">
    <SliderButton
      v-for="(button, index) in buttons"
      :key="index"
      :text="button"
      :slideNum="index + 1"
      :buttonWidth=33.3333
      :class="{'active' : index === activeSlide}"
      :progressStatus="progressStatus"
    />
  </div>
</template>

<script>
  import SliderButton from './SliderButton.vue'

  export default {
    name: 'slider-panel',
    props: {
      buttons: Array
    },
    components: {
      SliderButton
    },
    data: () => {
      return {
        activeIndex: 1,
        progressStatus: 40
      }
    },
    computed: {
      activeSlide: function () {
        return this.activeIndex
      }
    }
  }

</script>

<style lang="scss">
  .autodoc-slider__panel {
    width: 100%;
    height: 10vh;
    display: flex;
    align-items: stretch;
  }
</style>