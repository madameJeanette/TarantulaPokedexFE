<template>
  <div>
    <h4>Add your new spiders to your collection!</h4>
    <img
      src="../assets/1st spooder.jpg"
      alt="Red and black striped tarantula spider"
      width="700"
      height="auto"
    > 
    <div v-bind:key="tt.id" v-for="tt in tts">
      <TtItem v-bind:tt="tt" v-on:del-tt="$emit('del-tt',tt.id)"/>
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
  props: ["tts"]

  // mounted() {
  //   if (localStorage.getItem("tts")) {
  //     try {
  //       this.tts = JSON.parse(localStorage.getItem("tts"));
  //    } catch (e) {
  //       localStorage.removeItem("tts");
  //    }
  //  }
  // },
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

.input-form {
  width: 450px;
  font-size: 16px;
  background: #6820a3;
  padding: 30px 30px 15px 30px;
  border: 5px solid #341052;
  margin: auto;
}
.input-form input[type="submit"],
.input-form input[type="button"],
.input-form input[type="text"],
.input-form input[type="email"],
.input-form textarea,
.input-form label {
  font-family: Georgia, "Times New Roman", Times, serif;
  font-size: 16px;
  color: #fff;
}
.input-form label {
  display: block;
  margin-bottom: 10px;
}
.input-form label > span {
  display: inline-block;
  float: left;
  width: 150px;
}
.input-form input[type="text"],
.input-form input[type="email"] {
  background: transparent;
  border: none;
  border-bottom: 1px dashed #83a4c5;
  width: 275px;
  outline: none;
  padding: 0px 0px 0px 0px;
  font-style: italic;
}
.input-form textarea {
  font-style: italic;
  padding: 0px 0px 0px 0px;
  background: transparent;
  outline: none;
  border: none;
  border-bottom: 1px dashed #83a4c5;
  width: 275px;
  overflow: hidden;
  resize: none;
  height: 20px;
}

.input-form textarea:focus,
.input-form input[type="text"]:focus,
.input-form input[type="email"]:focus,
.input-form input[type="email"] :focus {
  border-bottom: 1px dashed #d9ffa9;
}

.input-form input[type="submit"],
.input-form input[type="button"] {
  background: #576e86;
  border: none;
  padding: 8px 10px 8px 10px;
  border-radius: 5px;
  color: #a8bace;
}
.input-form input[type="submit"]:hover,
.input-form input[type="button"]:hover {
  background: #394d61;
}
</style>
