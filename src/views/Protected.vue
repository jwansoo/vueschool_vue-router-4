<template>
  <div>
    <h1>Greetings, {{username}}</h1>
    <button @click="logout">Logout</button>
    <RouterLink :to="{name:'invoices'}">
      <button>Invoices</button>
    </RouterLink>
  </div>
</template>

<script setup>
import { useRoute,useRouter } from 'vue-router';
const username=window.user
const router=useRouter()
const logout=()=>{
  window.user=null
  router.push({name:'Home',query:{logout:null}})
}
</script>

<style lang="scss" scoped>

</style>