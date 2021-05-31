<template>
  <div id="app">
    <Slider :options="options" :slides="slides"/>
  </div>
</template>

<script>
  import Slider from './components/Slider.vue'

  export default {
    name: 'App',
    components: {
      Slider
    },
    data: () => {
      return {
        options: {
          slideChangeTime: 5000,
          autoplay: true,
          activeSlide: 1
        },
        slides: [
          {
            "albumId": 1,
            "id": 1,
            "title": "reprehenderit est deserunt velit ipsam",
            "accentTitle": "reprehenderit est deserunt velit ipsam",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.",
            "img": "https://picsum.photos/1600/900",
            "url": "https://some-link.com",
            "linkText": "Replace the front brake",
            "buttonTitle": 'Brake replacing',
          },
          {
            "albumId": 1,
            "id": 2,
            "title": "officia porro iure quia iusto qui ipsa ut modi",
            "accentTitle": "officia porro",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.",
            "img": "https://picsum.photos/1200/700",
            "url": "https://some-link.com",
            "linkText": "Replace the front brake",
            "buttonTitle": 'Driver shift control'
          },
          {
            "albumId": 1,
            "id": 3,
            "title": "How to replace the front brake pads",
            "accentTitle": "front brake pads",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.",
            "img": "https://picsum.photos/1920/1200",
            "url": "https://some-link.com",
            "linkText": "Replace the front brake",
            "buttonTitle": 'Some text in the button'
          },
        ]
      }
    }
  }
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap');
  #app {
    font-family: 'Roboto', Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  html {
    font-size: 10px;
  }
  body {
    margin: 0;
    font-size: 14px;
    line-height: 1.5;
  }
  * {
    box-sizing: border-box;
  }
  h1, h2, h3, h4, h5 {
    margin-top: 0;
    margin-bottom: 0;
  }
  p {
    margin: 0;
  }
  a {
    text-decoration: none;
    color: inherit;
    &:focus {
      color: inherit;
    }
    &:hover {
      color: inherit;
    }
  }

  @media (max-width: 1599px) {
    html {
      font-size: 8px;
    }
  }
</style>
