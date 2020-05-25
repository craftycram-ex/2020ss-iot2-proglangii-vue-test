<template>
      <tr>
          <th>{{meals.category}}</th>
          <td>{{meals.contentInformation}}</td>
          <td>{{meals.cost}}</td>
          <td>{{meals.day}}</td>
          <td>{{meals.downvotes}}</td>
          <td>{{meals.id}}</td>
          <td>{{meals.labels}}</td>
          <td>{{meals.name}}</td>
          <td>{{meals.upvotes}}</td>
      </tr>
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
</style>
