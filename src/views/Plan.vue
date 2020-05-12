<template>
  <div>
    <h1>{{msg}}</h1>
    <Dropdown :days="dropdownData"></Dropdown>
    <List :tableData="loadedData"></List>
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
      dropdownData: undefined
    }
  },
  mounted() {
    axios.get("http://localhost:3000/api/getData")
      .then(response => {
        this.loadedData = response.data;
        this.dropdownData = this.loadedData.map((essen) => essen.day);
        this.dropdownData = this.dropdownData.filter((a, b) => this.dropdownData.indexOf(a) === b)
      })
      .catch(err => {
        console.log(err)
      });

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
