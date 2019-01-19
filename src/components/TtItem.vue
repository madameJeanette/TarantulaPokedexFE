<template>
  <div class="tt-item">
    <p>{{tt.name}}</p>
  </div>
</template>

<script>
export default {
  name: "TtItem",
  props: ["tt"]
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

.is-complete {
  text-decoration: line-through;
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
