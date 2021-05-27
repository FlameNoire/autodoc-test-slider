<template>
  <div id="app">
    <Slider :slides="slides"/>
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
        slides: [
          {
            "albumId": 1,
            "id": 1,
            "title": "accusamus beatae ad facilis cum similique qui sunt",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.",
            "url": "https://picsum.photos/1920/1200",
            "buttonTitle": 'Some text in the button'
          },
          {
            "albumId": 1,
            "id": 2,
            "title": "reprehenderit est deserunt velit ipsam",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.",
            "url": "https://picsum.photos/1920/1200",
            "buttonTitle": 'Some text in the button'
          },
          {
            "albumId": 1,
            "id": 3,
            "title": "officia porro iure quia iusto qui ipsa ut modi",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.",
            "url": "https://picsum.photos/1920/1200",
            "buttonTitle": 'Some text in the button'
          },
        ]
      }
    }
  }
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  body {
    margin: 0;
  }
  * {
    box-sizing: border-box;
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
</style>
