<template>
  <div class="iltts">
    <h1>Tarantula PokeDex</h1>
    <img
      src="../assets/1st spooder.jpg"
      alt="Red and black striped tarantula spider"
      width="800"
      height="auto"
    >
    <h3>{{ message }}</h3>
    <input type="text" v-model="message">
    <button v-on:click="addTt()">Add tarantula</button>
    <button @click="removeTt(n)">Remove</button>
    <p>I love spiders</p>

    <ul>
      <li v-bind:key = "tt.id" v-for="tt in tts">{{tt}}</li>
    </ul>
  </div>
</template>
  <script>
export default {
  name: "IlTts",
  data() {
    return {
      message: null,
      tts: [""]
    };
  },
  mounted() {
    if (localStorage.getItem("tts")) {
      try {
        this.tts = JSON.parse(localStorage.getItem("tts"));
      } catch (e) {
        localStorage.removeItem("tts");
      }
    }
  },

  methods: {
    addTt: function() {
      var newTt = this.message.trim();
      if (!newTt) {
        return;
      }
      this.tts.push(newTt);
      this.message = "";
      this.saveTts();
    },
    removeTt(x) {
      this.tts.splice(x, 1);
      this.saveTts();
    },
    saveTts() {
      const parsed = JSON.stringify(this.tts);
      localStorage.setItem("tts", parsed);
    }
  }
};
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