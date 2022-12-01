<template>
  <TheNavigation />
<div class="container">

<router-view :key="$router.path" ></router-view>
</div>
</template>

<script setup>
import TheNavigation from './components/TheNavigation.vue'
</script>

<style>



.left-sidebar{
  width:20%;
}
.main-view{
  width:100%;
}
</style>