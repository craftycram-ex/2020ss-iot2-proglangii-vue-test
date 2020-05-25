<template>
  <div>
        <table>
          <th>Kategorie</th>
          <th>Infos</th>
          <th>Kosten</th>
          <th>Tag</th>
          <th>Downvotes</th>
          <th>ID</th>
          <th>Labels</th>
          <th>Name</th>
          <th>Upvotes</th>
          
          <Mahlzeit v-for="mealsFromTable in tableData" :key="mealsFromTable" :meals='mealsFromTable'></Mahlzeit>
        </table>
      <!--
      <div v-for="item in tableData" :key="item"><pre style="text-align:left;">{{item}}</pre></div>
      -->
  </div>
</template>

<script>

import Mahlzeit from '../components/Mahlzeit.vue'
export default {
  name: 'List',
  props: {
    tableData: String
  },
  components: {
    Mahlzeit
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
