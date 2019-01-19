<template>
  <div>
    <form>
      <input type="text" name="name" placeholder="New spider">
      <input type="text" latinName:="latinName" placeholder="latinName" v-model="tt">
      <input type="text" habitat:="habitat" placeholder="Habitat" v-model="tt">
      <input
        type="submit"
        value="submit"
        class="btn"
      >
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTt",
  latinName: "AddTt",
  habitat: "AddTt"
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>


