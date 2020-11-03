<template>
  <div>
    <carousel class="carousel">
      <carousel-slide v-for="n in slides" :index="n - 1">
        <div style="position:absolute; left:0; right:0; text-align:center; top:50%; color: #FFF; font-size:16px">Slide {{ n }}</div>
        <img :src="'http://placeimg.com/630/300/' + n " width="100%" height="50%">
      </carousel-slide>
    </carousel>
    <button @click="addSlide">Ajouter un slide</button>
    <button @click="removeSlide">Supprimer un slide</button>
    <todos v-model="todos"></todos>
  </div>
</template>

<script>
import Todos from './components/Todos'
import Carousel from './components/carousel/Carousel'
import CarouselSlide from './components/carousel/CarouselSlide'
export default {
  data() {
    return {
      slides: 5,
      todos: [{
        name: 'Demo',
        completed: true
      }]
    }
  },
  methods: {
    addTodo () {
      this.todos.push({
        name: 'Mohamed',
        completed: false
      })
    },
    addSlide () {
      this.slides++
    },    
    removeSlide () {
      this.slides--
    }
  },
  components: {
    Todos,
    Carousel,
    CarouselSlide
  }
}
</script>

<style>
  .carousel {
    position: relative;
    text-align: center;
    overflow: hidden;
  }

  .carousel__nav {
    position: absolute;
    top: 50%;
    margin-top: -31px;
    left: 10px;
    background: url(components/carousel/prev.png);
    width: 63px;
    height: 63px;
  }

  .carousel__nav.carousel__next {
    right: 10px;
    left: auto;
    background: url(components/carousel/next.png);

  }

  .carousel__pagination {
    position: absolute;
    bottom: 10px;
    left: 0;
    right: 0;
    text-align: center;
  }

  .carousel__pagination button {
    display: inline-block;
    width: 10px;
    height: 10px;
    background-color: #000;
    opacity: 0.8;
    border-radius: 10px;
    margin: 0.2px;
  }

  .carousel__pagination button.active{
    background-color: #fff;
  }
</style>
