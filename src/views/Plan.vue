<template>
  <div>
    <h1>{{msg}}</h1>
    {{loadedData}}
    <Dropdown></Dropdown>
    <List></List>
  </div>
</template>

<script>

import Dropdown from '../components/Dropdown.vue'
import List from '../components/List.vue'
import axios from 'axios'

export default {
  name: 'Plan',
  props: {
    msg: String
  },
  components: {
    Dropdown,
    List
  },
  data: function () {
    return {
      loadedData: undefined,
    }
  },
  mounted() {
    axios.get("http://localhost:3000/api/getData")
      .then(response => {
        this.loadedData = response.data;
      })
      .catch(err => {
        console.log(err)
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
