<template>
  <div id="nav">
<AppLink id="logo" to="/">Vue School Travel App</AppLink>
<AppLink
    v-for="destination in destinations"
    :key="destination.id"
    :to="{name:'destination.show', params:{id:destination.id, slug:destination.slug}}"

>{{destination.name}}</AppLink>

<AppLink :to="{name: 'protected'}">Dashboard</AppLink>

</div>
</template>

<script setup>
import sourceData from '../data.json'
const destinations=sourceData.destinations
</script>

<style lang="scss" scoped>

</style>