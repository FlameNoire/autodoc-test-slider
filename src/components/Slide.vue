<template>
  <div class="autodoc-slider__slide">
    <div class="autodoc-slider__slide-image">
      <img :src="img" alt=" ">
    </div>
    <div class="autodoc-slider__slide-content">
      <h2 class="autodoc-slider__slide-title">{{title}}</h2>
      <p class="autodoc-slider__slide-text">{{text}}</p>
      <a :href="link" class="autodoc-slider__slide-link">
        <span class="autodoc-slider__slide-link-text">{{linkText}}</span>
        <span class="autodoc-slider__slide-link-arrow">&rarr;</span>
      </a>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'slider-slide',
    props: {
      title: String,
      accentTitle: String || undefined,
      text: String,
      img: String,
      link: String,
      linkText: String,
    },
    computed: {
      newTitle() {
        let title = this.title
        return title
      }
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
    color: #3C4247;
    overflow: hidden;
    background-color: #fdfdfd;
  }
  .autodoc-slider__slide-image {
    position: relative;
    height: 100%;
    &:before {
      position: absolute;
      display: block;
      content: '';
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, rgba(255,255,255,1) 0%, rgba(255,255,255,0) 100%);
    }
    img {
      object-fit: cover;
      display: block;
      width: 100vw;
      height: 90vh;
    }
  }
  .autodoc-slider__slide-content {
    position: absolute;
    padding: 4vw 5vw;
    left: 0;
    top: 0;
    width: 55%;
    height: 100%;
    line-height: 1.5;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
  }
  .autodoc-slider__slide-title {
    margin-bottom: 3rem;
    font-size: 10rem;
    font-weight: 500;
    line-height: 1.35;
  }
  .autodoc-slider__slide-text {
    font-size: 21px;
    font-weight: 400;
  }
  .autodoc-slider__slide-link {
    margin-top: 4.5rem;
    font-size: 18px;
    font-weight: 500;
    color: #CC0000;
    transition: all .2s;
    display: flex;
    align-items: center;
    &:hover, &:focus {
      color: #CC0000;
      .autodoc-slider__slide-link-arrow {
        transform: translateX(10px);
      }
      .autodoc-slider__slide-link-text {
        &:after {
          width: 0;
        }
      }
    }
  }
  .autodoc-slider__slide-link-text {
    position: relative;
    margin-right: 10px;
    &:after {
      position: absolute;
      display: block;
      content: '';
      bottom: -1px;
      left: 0;
      width: 100%;
      height: 1px;
      background-color: crimson;
      transition: all .2s;
    }
  }
  .autodoc-slider__slide-link-arrow {
    transform: translateX(0);
    transition: all .2s;
  }
</style>