<template>
  <div id="app">
    <IlTts/>
    <Tt/>
  </div>
</template>

<script>
import IlTts from "./components/IlTts";
import Tt from "./components/Tt";

export default {
  name: "App",
  components: {
    IlTts,
    Tt
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

