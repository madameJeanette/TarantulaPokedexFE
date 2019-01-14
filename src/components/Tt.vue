<template>
  <div class="tt">
    {{ tt }}
  </div>
</template>

<script>

import axios from 'axios'

export default {
  name: 'Tt',
  data () {
    return {
      tt: {} //return spiders
    }
  },
  created () {
    axios.get('http://localhost:8000/api/tarantulas')
      .then(response => {
        //console.log(response)
        this.tt = response.data
      })
      .catch(err => {
        console.log(err)
      })
  }
}
</script>

<style scoped></style>