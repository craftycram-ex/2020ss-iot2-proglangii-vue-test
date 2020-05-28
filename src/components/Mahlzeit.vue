<template>
      <div>
          <h5>{{meals.category}}</h5>
          <hr>
          <h3>{{meals.name}}</h3>
          {{meals.cost.students}} €<br>
          <div class="ci" v-for="ci in meals.contentInformation" :key="ci"><small>{{ci}}</small></div>

          <br>
          <!--
          {{meals.cost}}
          {{meals.day}}
          {{meals.downvotes}}
          {{meals.id}}
          {{meals.labels}}
          {{meals.upvotes}}
          -->
          
      </div>
</template>

<script>
export default {
  name: 'Mahlzeit',
  props: {
    meals: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.ci {
  font-size: 8pt;
  display: inline-block;
  margin-right: 10px;
}
</style>
