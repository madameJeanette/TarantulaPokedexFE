<template>
  <div id="app">
    <Header/>
    <AddTt v-on:add-tt="addTt"/>
    <Tts v-bind:tts="tts" v-on:del-tt="deleteTt"/>
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Tts from "./components/Tts";
import AddTt from "./components/AddTt";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Tts,
    AddTt
  },

  data() {
    return {
      tts: []
    };
  },

  methods: {
    deleteTt(id) {
      axios
        .delete(`http://localhost:8000/api/tarantulas/${id}`)
        .then(response => (this.tts = this.tts.filter(tt => tt.id !== id)))
        .catch(err => console.log(err));
    },

    addTt(newTt) {
      const { name, latinName, habitat, collected } = newTt;

      axios
        .post("http://localhost:8000/api/tarantulas", {
          name,
          latinName,
          habitat,
          collected
        })

        .then(response => (this.tts = [...this.tts, response.data]))
        .catch(err => console.log(err));
    }
  },
  created() {
    axios
      .get("http://localhost:8000/api/tarantulas")
      .then(response => (this.tts = response.data.items))
      .catch(err => console.log(err));
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

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>

