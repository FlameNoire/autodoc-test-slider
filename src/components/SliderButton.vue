<template>
  <a href="#"
     class="autodoc-slider__button"
     @click.prevent="buttonClick"
     @mouseover.self="mouseover"
     @mouseleave.self="mouseleave"
     :style="{ width: buttonWidth + '%' }"
  >
    <div class="autodoc-slider__button-progress">
      <div v-if="autoplay" class="autodoc-slider__button-progress-bar">
        <span ref="progressBar"></span>
      </div>
    </div>
    <div class="autodoc-slider__button-number">{{ '0' + (slideNum + 1) }}</div>
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
      progressStatus: Boolean,
      progressDuration: Number,
      autoplay: Boolean,
    },
    data: () => {
      return {
        pause: false,
        progressValue: 0
      }
    },
    computed: {
      isPause: function () {
        return this.pause
      },
      getProgressValue: function () {
        return this.progressValue
      }
    },
    methods: {
      buttonClick() {
        if ( !this.progressStatus ) {
          // this.pause = true
          this.$emit('slideChangeHandler', this.slideNum)
        }
      },
      mouseover() {
        if ( this.progressStatus && this.autoplay ) {
          this.pause = true
          cancelAnimationFrame(this.requestId)
          this.progressAnimationReverse()
          this.$emit('mouseoverHandler', true)
        }
      },
      mouseleave() {
        if ( this.progressStatus && this.autoplay ) {
          this.pause = false
          cancelAnimationFrame(this.requestId)
          this.progressAnimation()
          this.$emit('mouseleaveHandler', false)
        }
      },
      progressAnimation() {
        let tween = this.$refs.progressBar
        let step = 100 / (60 * this.progressDuration / 1000)
        this.progressValue = 0
        let animation = () => {
          if ( this.getProgressValue < 100 && !this.isPause ) {
            this.progressValue += step
            tween.style.width = this.getProgressValue + '%'
            requestAnimationFrame(animation)
          }
        }
        this.requestId = requestAnimationFrame(animation)
      },
      progressAnimationReverse() {
        let tween = this.$refs.progressBar
        let step = 2
        let animation = () => {
          if ( this.getProgressValue > 0 && this.isPause ) {
            this.progressValue -= step
            tween.style.width = this.getProgressValue + '%'
            requestAnimationFrame(animation)
          }
          if ( this.getProgressValue <= 0 ) {
            this.progressValue = 0
            tween.style.width = '0%'
          }
        }
        this.requestId = requestAnimationFrame(animation)
      },
    },
    watch: {
      progressStatus: function (newValue) {
        if (newValue && this.autoplay)
          cancelAnimationFrame(this.requestId)
          this.progressAnimation()
      },
    },
    mounted() {
      if ( this.progressStatus && this.autoplay )
        this.progressAnimation()
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
          }
        }
      }
      .autodoc-slider__button-progress {
        visibility: visible;
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
    padding-right: 10px;
    width: 100%;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
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
    height: calc(4vh + 1px);
    margin-bottom: -1px;
    display: flex;
    align-items: center;
    background-color: #CC0000;
    pointer-events: none;
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
    }
  }
</style>