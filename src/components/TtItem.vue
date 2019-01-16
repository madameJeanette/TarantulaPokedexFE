<template>

  <div class="tt-item">
   <p>{{tt.name}}</p>
  </div>
</template>

<script>
export default {
    name: "TtItem",
    props:["tt"]
}
</script>

<style scoped>
.tt-item {
    background: lightcoral;
    color: white;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}
</style>
