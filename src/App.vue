<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div id ="app">
    <Todo-app>
      
    </Todo-app>


  </div>

</template>

<script>
import TodoApp from './components/TodoApp.vue'

export default {
  name: 'App',
  components: {
    TodoApp
  }
}
</script>

