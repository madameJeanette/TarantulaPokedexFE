<template>
  <div>
    <!-- <h4>Add your new spiders to your collection!</h4> -->
    <!-- <img
      src="../assets/1st spooder.jpg"
      alt="Red and black striped tarantula spider"
      width="700"
      height="auto"
    >  -->
    <div v-bind:key="tt.id" v-for="tt in tts">
      <TtItem v-bind:tt="tt" v-on:del-tt="$emit('del-tt',tt.id)"/>
    </div>
  </div>
</template>

<script>
import TtItem from './TtItem.vue';

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

</style>
