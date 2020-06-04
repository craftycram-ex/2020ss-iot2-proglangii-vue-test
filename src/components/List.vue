<template>
  <div>
    <!--
    <th>Kategorie</th>
    <th>Infos</th>
    <th>Kosten</th>
    <th>Tag</th>
    <th>Downvotes</th>
    <th>ID</th>
    <th>Labels</th>
    <th>Name</th>
    <th>Upvotes</th>
    -->

  <b-card-group columns>
    <b-card v-for="meal in tableData" :key="meal" img-src="https://picsum.photos/200">
      <b-card-text>
      <Mahlzeit class="mahlzeit" :meal='meal'></Mahlzeit>
      </b-card-text>
    </b-card>
  </b-card-group>

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
  .mahlzeit {


    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 50px;
  }
</style>
