<template>
  <div class="autodoc-slider__panel">
    <SliderButton
      v-for="(button, index) in buttons"
      :key="index"
      :text="button.text"
      :slideNum="index + 1"
      :buttonWidth=33.3333
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
    }
  }

</script>

<style lang="scss">
  .autodoc-slider__panel {
    width: 100%;
    height: 10vh;
    display: flex;
    align-items: stretch;
    border: 1px solid #333;
  }
</style>