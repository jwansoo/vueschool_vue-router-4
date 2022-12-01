<template>
  <div class="home">
    <h1>Home</h1>
    <h1>All Destinations</h1>
    <button @click="addDynamicRoute">Add Dynamic Router</button>
    <router-link to="/dynamic">Visit Dynamic Route</router-link>
    <div class="destnations">
    <router-link
    v-for="destination in destinations"
    :key="destination.id"
    :to="{name:'destination.show', params:{id:destination.id,slug:destination.slug}}"
    >
    <h2>{{destination.name}}</h2>
    <img :src="`/public/images/${destination.image}`" :alt="destination.name" />
   </router-link>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'
import sourceData from '../data.json'
import { useRoute, useRouter } from 'vue-router';
import { isNavigationFailure, NavigationFailureType } from 'vue-router';
const destinations=ref(sourceData.destinations)
const router=useRouter()
const triggerRouterError= async ()=>{
  const navigationFailure= await router.push('/')
  if(isNavigationFailure(navigationFailure, NavigationFailureType.duplicated)){
    console.log(navigationFailure.to);
    console.log(navigationFailure.from)
  }else{

  }
}
function addDynamicRoute(){
  router.addRoute({
    name:'dynamic',
    path:'/dynamic',
    component:()=>import('../views/Login.vue')
  })
  router.removeRoute('dynamic')
}
</script>

<style lang="scss" scoped>

</style>