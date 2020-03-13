<template>
  <div id="app">
    <previewer></previewer>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css"
import "font-awesome/css/font-awesome.css"
import Previewer from './components/Previewer'


export default {
  name: 'App',
  components: {
    Previewer
  }
}
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100vh;
}
</style>
