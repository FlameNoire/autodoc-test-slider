<template>
  <div id="app">
    <Slider :options="options" :slides="slides"/>
    <div class="sample-text">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet, at dolorem explicabo illo minima minus natus nulla optio praesentium quod. Ab asperiores consequuntur dolorum ea expedita nesciunt qui totam unde! Autem, cum earum. Aliquid aperiam aspernatur, at autem culpa expedita ipsa labore libero molestiae nobis odit quos recusandae repellat, sint unde vel veniam. A ab adipisci alias aliquam consectetur cupiditate delectus hic maiores minima nam nisi pariatur, placeat quisquam quod reprehenderit sapiente temporibus veniam? Ad cumque deleniti, doloremque doloribus ducimus eos ipsa laborum maxime neque perspiciatis quam quas reprehenderit voluptate? Commodi culpa iste natus rem sit tempore ut voluptates! Accusamus ad fugiat ipsum laboriosam officia perferendis quas rerum vitae. Inventore, ipsam, nihil. Incidunt mollitia praesentium soluta tempore vitae voluptates. Aperiam at culpa dolores eos hic ipsa quod? Adipisci aperiam assumenda at atque aut autem cum dolorum ducimus ea earum eveniet excepturi expedita facere hic id, impedit ipsa iste iure labore magni maxime molestiae neque nobis pariatur placeat praesentium quidem quisquam quos repellendus saepe similique ut voluptas voluptatum? Ab aut dolor itaque tempora voluptatum. Adipisci aliquid fugiat odit quam repellat, tempora! A ad assumenda dolor, dolorem doloribus fugiat iure laboriosam libero magnam magni, odio, provident quia quo. Accusantium aliquid aperiam fugit ipsa laboriosam minus officia pariatur qui reiciendis soluta. Asperiores corporis cumque ducimus eius, enim fugiat, harum hic in iure iusto magni minima nisi perspiciatis praesentium quasi quis reprehenderit totam voluptas. Aut, consectetur distinctio dolor dolore, earum exercitationem in libero nemo nesciunt porro quaerat quo tempora tempore, tenetur voluptatem? Deleniti dicta doloremque earum explicabo, natus optio quia quisquam reprehenderit sed sunt. Blanditiis, quis repellat. Placeat, quia quidem! Adipisci commodi consectetur cupiditate eligendi expedita facere facilis impedit incidunt iste iure laborum, magni, natus neque nisi obcaecati pariatur placeat possimus quae qui quibusdam quod, recusandae reiciendis repellat repudiandae saepe suscipit tempora temporibus vel velit voluptate. Cumque illum itaque iure natus officia perferendis quia quis ullam unde vitae! Consequuntur in officiis placeat reiciendis tempore. Accusamus aspernatur aut, culpa dolor dolorem eius, error excepturi expedita inventore laboriosam maiores odio omnis praesentium qui quibusdam rerum veritatis vitae voluptas. A aut corporis laborum magni minima mollitia possimus qui quibusdam quos tenetur! Accusantium atque beatae blanditiis cumque dignissimos, dolorem error, excepturi fugit illo inventore nihil odio perferendis sed sequi ullam velit veritatis! Accusamus, atque deleniti dolore eaque eveniet in laboriosam non possimus qui recusandae! Aliquam aliquid animi consequuntur culpa doloremque dolores earum eum exercitationem itaque magni molestias reprehenderit similique sint vel, vero. Amet cupiditate deleniti doloribus magni minima mollitia, nam numquam tempore! Asperiores assumenda deleniti doloremque doloribus, ducimus expedita hic id porro possimus praesentium quasi quis, reiciendis suscipit tempore ullam! Ad adipisci amet aperiam harum incidunt inventore, ipsa laudantium magni, nostrum obcaecati qui quisquam repudiandae totam! Commodi dolore inventore maxime sequi sit. Assumenda at atque consequuntur deleniti dicta ea earum, eveniet explicabo magni maxime, natus nemo officia repellendus reprehenderit repudiandae tenetur vel! Accusamus alias assumenda consectetur, deleniti dolore doloribus enim fugiat ipsum laudantium magnam maxime mollitia non perferendis quae, quaerat quia ratione rem saepe veritatis voluptas, voluptates voluptatum.
    </div>
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
          startSlide: 1
        },
        slidesData: [
          {
            "id": 0,
            "title": "How to replace the front brake pads",
            "accentTitle": "front brake pads",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
            "img": require('./assets/img/pexels-vincenzo-malagoli-1920x1280.jpg'),
            // "img": "https://picsum.photos/1600/900",
            "url": "https://some-link.com",
            "linkText": "Replace the front brake",
            "buttonTitle": 'Brake replacing',
          },
          {
            "id": 1,
            "title": "Driver shift control: features, advantages & disadvantages",
            "accentTitle": "Driver shift control:",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
            "img": require('./assets/img/pexels-mike-2560x1438.jpg'),
            // "img": "https://picsum.photos/1200/700",
            "url": "https://some-link.com",
            "linkText": "How it works",
            "buttonTitle": 'Driver shift control'
          },
          {
            "id": 2,
            "title": "What is Sportmatic",
            "accentTitle": "Sportmatic",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
            "img": require('./assets/img/pexels-kelson-downes-1800x1200.jpg'),
            // "img": "https://picsum.photos/1920/1200",
            "url": "https://some-link.com",
            "linkText": "Operating principle",
            "buttonTitle": 'Sportmatic'
          },
          {
            "id": 3,
            "title": "How to replace the front brake pads",
            "accentTitle": "front brake pads",
            "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
            "img": require('./assets/img/689-1600x900.jpg'),
            // "img": "https://picsum.photos/1600/900",
            "url": "https://some-link.com",
            "linkText": "Replace the front brake",
            "buttonTitle": 'Brake replacing',
          },
          // {
          //   "id": 4,
          //   "title": "Driver shift control: features, advantages & disadvantages",
          //   "accentTitle": "Driver shift control:",
          //   "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
          //   "img": require('./assets/img/426-1200x700.jpg'),
          //   // "img": "https://picsum.photos/1200/700",
          //   "url": "https://some-link.com",
          //   "linkText": "How it works",
          //   "buttonTitle": 'Driver shift control'
          // },
          // {
          //   "id": 5,
          //   "title": "What is Sportmatic",
          //   "accentTitle": "Sportmatic",
          //   "text": "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
          //   "img": require('./assets/img/392-1920x1200.jpg'),
          //   // "img": "https://picsum.photos/1920/1200",
          //   "url": "https://some-link.com",
          //   "linkText": "Operating principle",
          //   "buttonTitle": 'Sportmatic'
          // },
        ]
      }
    },
    computed: {
      slides() {
        return this.slidesData
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
    &::-webkit-scrollbar {
      width: 0;
    }
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

  .sample-text {
    padding: 100px;
    font-size: 18px;
  }

  @media (max-width: 1599px) {
    html {
      font-size: 8px;
    }
  }
</style>
