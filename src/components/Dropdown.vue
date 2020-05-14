<template>
  <div>
    <span>Wochentag</span>
  <select name="Wochentag" id="selectBox">
          <option v-for="day in days" :key="day">{{day}}</option>
        </select>
  </div>
</template>

<script>
export default {
  name: 'Dropdown',
  props: {
    days: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
