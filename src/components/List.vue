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

  <b-row class="mahlzeiten">
    <b-card v-for="meal in tableData" :key="meal.id" tag="article" img-src="https://picsum.photos/600/300">
      <b-card-text>
      <Mahlzeit class="nb-5"  :meal='meal'></Mahlzeit>
      </b-card-text>
    </b-card>
  </b-row>

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
    tableData: Array
  },
  components: {
    Mahlzeit
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .mahlzeit {
    margin-top: 15vh;
    margin-left: auto;
    margin-right: auto;
    padding: 0 calc(69px/0.3);
  }
</style>
