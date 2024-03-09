<template>
  <ToDoList/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import CountIncrementer from './components/CountIncrementer.vue'
import ToDoList from './components/ToDoList.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // CountIncrementer,
    ToDoList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
