<template>
  <div id="app">
   
   <IlTts/>
  </div>
</template>

<script>

import IlTts from './components/IlTts'

export default {
  name: 'App',
  components: {
    
    IlTts
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

