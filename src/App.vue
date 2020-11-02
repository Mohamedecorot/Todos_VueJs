<template>
  <div>
    <carousel class="carousel">
      <carousel-slide>
        <div style="position:absolute; left:0; right:0; text-align:center; top:50%; color: #FFF; font-size:16px">salut les gens</div>
        <img src="https://picsum.photos/630/300" width="100%">
      </carousel-slide>
      <carousel-slide>
        <div style="position:absolute; left:0; right:0; text-align:center; top:50%; color: #FFF; font-size:16px">Aurevoir les gens</div>
        <img src="https://picsum.photos/630/300" width="100%">
      </carousel-slide>
    </carousel>
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

</style>
