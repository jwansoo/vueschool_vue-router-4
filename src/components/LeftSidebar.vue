<template>
  <ul>
    <li><RouterLink :to="{name:'protected'}">Dashboard</RouterLink></li>
    <li><RouterLink :to="{name:'invoices'}">Invoice</RouterLink></li>
  </ul>
</template>

<script setup>

</script>

<style scoped>
ul{
  background:white;
  padding:10px;
  list-style: none;
  margin-right: 20px;
}
li{
  margin:10px;
}
</style>