<template>
  <div id="app">
    <Tts v-bind:tts="tts"/>
    <Tt/>
  </div>
</template>

<script>
import Tts from "./components/Tts";

export default {
  name: "App",
  components: {
    Tts
  },
  data() {
    return {
      tts: [
        {
          id: 1,
          name: "Grace",
          latinName: "Yberapora diversipes",
          collected: true
        },
        {
          id: 1,
          name: "Scarlett",
          latinName: "Caribena diversipes",
          collected: true
        },
        {
          id: 1,
          name: "Mr. Fuzzy ",
          latinName: "brachypelma xxx",
          collected: false
        }
      ]
    };
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

