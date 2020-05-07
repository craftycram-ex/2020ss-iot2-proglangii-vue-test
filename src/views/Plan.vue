<template>
  <div>
    <h1>{{msg}}</h1>
    <span>Wochentag</span>
    <!-- Add components here -->
  </div>
</template>

<script>
export default {
  name: 'Plan',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
