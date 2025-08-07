<script setup>
import {ref, defineProps} from "vue";

const props = defineProps(['tablica'])




</script>


<template>
  <ul>
    <li v-for="(zad, index) in tablica" :key='index' >{{zad}} <button>gotowe</button>
  <button >usun</button></li>
  </ul>
</template>


<style scoped>

</style>