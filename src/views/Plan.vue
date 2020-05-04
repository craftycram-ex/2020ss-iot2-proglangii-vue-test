<template>
  <div>
    <h1>{{msg}}</h1>
    <span>Wochentag</span>
  <select name="Wochentag" id="selectBox">
          <option>Montag</option>
          <option>Dienstag</option>
          <option>Mittwoch</option>
          <option>Donnerstag</option>
          <option>Freitag</option>
        </select>
    
        <br>
        <table>
          <tr>Kategorie</tr>
          <tr>Infos</tr>
          <tr>Kosten</tr>
          <tr>Tag</tr>
          <tr>Downvotes</tr>
          <tr>ID</tr>
          <tr>Labels</tr>
          <tr>Name</tr>
          <tr>Upvotes</tr>
        </table>
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
