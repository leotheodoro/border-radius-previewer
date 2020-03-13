<template>
  <div id="app">
    <h1>Border Radius Previewer</h1>
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
  background-color: #b8c6db;
  background-image: linear-gradient(315deg, #b8c6db 0%, #f5f7fa 74%);
}

#app h1 {
  margin: 0 auto;
  margin-bottom: 50px;
  font-size: 72px;
  background: -webkit-linear-gradient(315deg, #2a2a72 0%, #009ffd 74%);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>
