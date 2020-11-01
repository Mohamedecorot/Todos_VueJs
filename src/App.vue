<template>
  <div>
    {{ todos }}
    <todos v-model="todos"></todos>
    <todos v-model="todos"></todos>
    <button @click="addTodo">Ajouter une tâche</button>
  </div>
</template>

<script>
import Todos from './components/Todos'
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
    Todos
  }
}
</script>

<style>
</style>
