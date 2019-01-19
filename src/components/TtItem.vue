<template>
  <div class="tt-item" v-bind:class="{'is-collected':tt.collected}">
   
   
   <input type="checkbox" v-on:change="markCollected">
   <h4> {{tt.name}}</h4>
   <button @click="$emit('del-tt',tt.id)" class='del'>x</button>
   <p>
   Latin name: {{tt.latinName}}<br>
   Habitat: {{tt.habitat}}<br>
   In collection: {{tt.collected}}
   </p>
  </div>
</template>

<script>
export default {
  name: "TtItem",
  props: ["tt"],
  methods: {
    markCollected() {
      this.tt.collected = !this.tt.collected;
    }
  }
};
</script>

<style scoped>
.tt-item {
  width: 800px;
  font-size: 20px;
 
  background: #f4f4f4;
  color: black;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
  margin: auto;
  
}

.is-collected {
  text-decoration: underline;
  text-decoration-style:double;
  text-decoration-color:lightseagreen;
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
