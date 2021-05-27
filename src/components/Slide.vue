<template>
  <div class="autodoc-slider__slide">
    <div class="autodoc-slider__slide-image">
      <img :src="url" alt=" ">
    </div>
    <div class="autodoc-slider__slide-content">
      <h2 class="autodoc-slider__slide-title">{{title}}</h2>
      <p class="autodoc-slider__slide-text">{{text}}</p>
      <a href="#" class="autodoc-slider__slide-link">Learn more &rarr;</a>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'slider-slide',
    props: {
      title: String,
      text: String,
      url: String
    }
  }
</script>

<style lang="scss">
  .autodoc-slider__slide {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    font-size: 36px;
    color: #ffffff;
    overflow: hidden;
  }
  .autodoc-slider__slide-image {
    img {
      object-fit: cover;
    }
  }
  .autodoc-slider__slide-content {
    position: absolute;
    left: 0;
    top: 0;
    width: 50%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
  }
  .autodoc-slider__slide-text {
    font-size: 24px;
  }
  .autodoc-slider__slide-link {
    font-size: 16px;
    color: crimson;
  }
</style>