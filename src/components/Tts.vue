<template>
  <div>
    <h1>Tarantula PokeDex</h1>
    <img
      src="../assets/1st spooder.jpg"
      alt="Red and black striped tarantula spider"
      width="800"
      height="auto"
    >
    <h3> Add your new spiders to your collection!</h3>
    <input type="text" v-model="tt">
    
  <button v-on:click="addTt()">Add tarantula</button>
   <button @click="removeTt(n)">Remove</button>

    <div v-bind:key="tt.id" v-for="tt in tts">
      <TtItem v-bind:tt="tt"/>
    </div>
  </div>
</template>

<script>
import TtItem from "./TtItem.vue";

export default {
  name: "Tts",
  components: {
    TtItem
  },
  props: ["tts"],

 // mounted() {
 //   if (localStorage.getItem("tts")) {
 //     try {
 //       this.tts = JSON.parse(localStorage.getItem("tts"));
  //    } catch (e) {
 //       localStorage.removeItem("tts");
  //    }
  //  }
 // },

  methods: {
    addTt: function() {
    var newTt = this.tt.trim();
     if (!newTt) {
        return;
      }
      this.tts.push(newTt);
      this.tt = "";
      this.saveTts();
    },
    removeTt(x) {
      this.tts.splice(x, 1);
      this.saveTts();
    },
   saveTts() {
     const parsed = JSON.stringify(this.tts);
 //     localStorage.setItem("tts", parsed);
   }
  }
}
</script>
<style scoped>
h1,
h2 {
  font-weight: normal;
}
h3 {
  color: hsl(288, 91%, 22%);
}
p {
  font-weight: bold;
}
ul {
  list-style-type: none;
  padding: 0;
  color: hsl(288, 91%, 22%);
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: hsl(288, 91%, 22%);
}
</style>