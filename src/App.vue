<template>
  <div>
    <carousel>
      <carousel-slide>
        salut les gens
      </carousel-slide>
      <carousel-slide>
        Aurevoir les gens
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
</style>
