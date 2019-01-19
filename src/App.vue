<template>
  <div id="app">
     <h1>Tarantula PokeDex</h1>
    

    <Tts v-bind:tts="tts"/>
    
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
     tts: [],
             
    }
  },

  methods: {
    removeTt(id){
      axios.delete(`http://localhost:8000/api/tarantulas/${id}`)
      .then(res => this.tts.filter(tt => tt.id !== id))
      .catch(err => console.log(err));
    },

    addTt(newTt) {
      const { name, latinName, habitat} = newTt;
      
      axios.post("http://localhost:8000/api/tarantulas", {
        name, latinName, habitat
      })
      .then(res =>  this.tts = [...this.tts, res.data])
      .catch(err => console.log(err));
    }
     
  }
  
  
}
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

