<template>
  <a href="#" @click.prevent class="autodoc-slider__button" :style="{ width: buttonWidth + '%' }">
    <div class="autodoc-slider__button-progress">
      <div class="autodoc-slider__button-progress-bar">
        <span></span>
      </div>
    </div>
    <div class="autodoc-slider__button-number">{{ '0' + slideNum }}</div>
    <div class="autodoc-slider__button-text">{{ text }}</div>
  </a>
</template>

<script>
  export default {
    name: 'slider-button',
    props: {
      buttonWidth: Number,
      slideNum: Number,
      text: String
    }
  }
</script>

<style lang="scss">
  .autodoc-slider__button {
    font-size: 16px;
    display: flex;
    align-items: flex-start;
    border: 1px solid #333;
  }
</style>