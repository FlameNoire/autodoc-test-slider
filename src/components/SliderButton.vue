<template>
  <a href="#" class="autodoc-slider__button" @click.prevent="$emit('slideChangeHandler', slideNum)" :style="{ width: buttonWidth + '%' }">
    <div class="autodoc-slider__button-progress">
      <div class="autodoc-slider__button-progress-bar">
        <span :style="{ width: progressStatus + '%' }"></span>
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
      text: String,
      progressStatus: Number
    }
  }
</script>

<style lang="scss">
  .autodoc-slider__button {
    padding: 15px 20px;
    position: relative;
    font-size: 16px;
    font-weight: 500;
    display: flex;
    align-items: flex-start;
    &.active {
      color: #ffffff;
      background-color: #CC0000;
      .autodoc-slider__button-progress {
        visibility: visible;
      }
      .autodoc-slider__button-number {
        opacity: 0.8;
      }
    }
  }
  .autodoc-slider__button-number {
    flex-shrink: 0;
    opacity: 0.3;
  }
  .autodoc-slider__button-text {
    width: 100%;
    text-align: center;
  }
  .autodoc-slider__button-progress {
    visibility: hidden;
    padding-left: 20px;
    padding-right: 20px;
    position: absolute;
    bottom: 100%;
    left: 0;
    width: 100%;
    height: 4vh;
    display: flex;
    align-items: center;
    background-color: #CC0000;
  }
  .autodoc-slider__button-progress-bar {
    position: relative;
    width: 100%;
    height: 5px;
    background-color: rgba(#fff, 0.7);
    span {
      position: absolute;
      height: 100%;
      background-color: #fff;
    }
  }
</style>