<template>
  <div class="page-index">
    <div class="row">
      <div class="col-md-8">
        <carousel :perPage="1" :paginationSize="20"">
          <slide v-for="item in slides" :key="item.id">
            <div class="text">{{ item.text }}</div>
            <img :src="item.image" alt="">
          </slide>
        </carousel>
      </div>
      <div class="col-md-4">

      </div>
    </div>
  </div>
</template>

<script>
import { Carousel, Slide } from 'vue-carousel'
export default {
  name: 'page-index',
  components: {
    Carousel,
    Slide
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      slides: [
        {id: 1, text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua 1', image: require('../assets/slider/slide-1.jpg')},
        {id: 2, text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua 2', image: require('../assets/slider/slide-2.jpg')},
        {id: 3, text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua 3', image: require('../assets/slider/slide-3.jpg')}
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

</style>
