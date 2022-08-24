<template>
  <div class="navbar" :id="scrollTop">
    <h1>Spellbook</h1>
  </div>
</template>

<script>
  export default {
    name:"NavBar",
    props: ["scrollTop"]
  }
</script>

<style scoped>
.navbar{
  font-family: 'Lobster', cursive;
  color: #000000;
}

.navbar h1{
  color: #333333;
}

</style>