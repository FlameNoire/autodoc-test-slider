<template>
  <a href="#"
     class="autodoc-slider__button"
     @click.prevent="$emit('slideChangeHandler', slideNum)"
     @mouseover="$emit('mouseoverHandler')"
     @mouseleave="$emit('mouseleaveHandler')"
     :style="{ width: buttonWidth + '%' }">
    <div class="autodoc-slider__button-progress">
      <div v-if="isProgress" class="autodoc-slider__button-progress-bar">
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
      text: String,
      progressStatus: Number,
      isProgress: Boolean
    }
  }
</script>

<style lang="scss">
  @keyframes progress {
    0% {
      width: 0;
    }
    100% {
      width: 100%;
    }
  }
  .autodoc-slider__button {
    padding: 15px 20px;
    position: relative;
    font-size: 16px;
    line-height: 22px;
    font-weight: 500;
    display: flex;
    align-items: flex-start;
    &.active {
      color: #ffffff;
      background-color: #CC0000;
      &:hover {
        .autodoc-slider__button-progress-bar {
          span {
            width: 0;
            transition: width .5s linear;
            animation: none;
          }
        }
      }
      .autodoc-slider__button-progress {
        visibility: visible;
      }
      .autodoc-slider__button-progress-bar {
        span {
          width: 100%;
        }
      }
      .autodoc-slider__button-number {
        opacity: 0.8;
      }
    }
  }
  .autodoc-slider__button-number {
    padding-right: 10px;
    flex-shrink: 0;
    opacity: 0.3;
  }
  .autodoc-slider__button-text {
    width: 100%;
    height: 44px;
    overflow: hidden;
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
      width: 0;
      background-color: #fff;
      transition: width 5s linear;
      animation: progress 5s 0s linear backwards;
    }
  }
</style>