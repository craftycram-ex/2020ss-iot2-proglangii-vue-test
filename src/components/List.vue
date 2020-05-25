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

          <tr v-for="entry in tableData" :key="entry">
            <th>{{entry.category}}</th>
            <td>{{entry.contentInformation}}</td>
            <td>{{entry.cost}}</td>
            <td>{{entry.day}}</td>
            <td>{{entry.downvotes}}</td>
            <td>{{entry.id}}</td>
            <td>{{entry.labels}}</td>
            <td>{{entry.name}}</td>
            <td>{{entry.upvotes}}</td>
          </tr>

        </table>

        <Mahlzeit></Mahlzeit>
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
