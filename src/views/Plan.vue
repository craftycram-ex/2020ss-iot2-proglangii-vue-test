<template>
  <div>
    <h1>{{msg}}</h1>
    <Dropdown></Dropdown>
    <List></List>
  </div>
</template>

<script>

import Dropdown from '../components/Dropdown.vue'
import List from '../components/List.vue'

export default {
  name: 'Plan',
  props: {
    msg: String
  },
  components: {
    Dropdown,
    List
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
