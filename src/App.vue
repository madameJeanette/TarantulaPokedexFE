<template>
  <div id="app">
    <h1>Tarantula PokeDex</h1>

    <Tts v-bind:tts="tts" v-on:del-tt="deleteTt"/>
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
          name: "sjaak",
          latinName: "geen idee",
          habitat: "kelder",
          collected: true
        },

        {
          id: 2,
          name: "teo",
          latinName: "geen idee",
          habitat: "boom",
          collected: false
        },
        {
          id: 3,
          name: "teo2",
          latinName: "geen idee",
          habitat: "boom",
          collected: false
        },
        {
          id: 4,
          name: "teo3",
          latinName: "geen idee",
          habitat: "boom",
          collected: false
        },
        {
          id: 5,
          name: "teo4",
          latinName: "geen idee",
          habitat: "boom",
          collected: false
        },
        {
          id: 6,
          name: "teo5",
          latinName: "geen idee",
          habitat: "boom",
          collected: false
        },
        {
          id: 7,
          name: "teo6",
          latinName: "geen idee",
          habitat: "boom",
          collected: false
        }
      ]
    };
    // },
    //  created() {
    //   axios
    //     .get("http://localhost:8000/api/tarantulas?_limit=5")
    //     .then(response => (this.tts = response.data.items))
    //     .catch(error => console.log(error));
  },

  methods: {
    deleteTt(id) {
      this.tts = this.tts.filter(tt => tt.id !== id);
    }
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

