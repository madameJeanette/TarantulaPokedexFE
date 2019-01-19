<template>
  <div id="app">
    <Header />
    <AddTt/>
    <Tts v-bind:tts="tts"
    v-on:del-tt="deleteTt"/>
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Tts from "./components/Tts";
import AddTt from "./components/AddTt";


export default {
  name: "App",
  components: {
    Header,
    Tts,
    AddTt
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
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn{
  display: inline-block;
  border:none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}

</style>

