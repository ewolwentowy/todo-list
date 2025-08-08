<script setup>
import { ref } from 'vue'

const zadanie = ref('')
const emit = defineEmits(['dodaj'])

function przekaz() {
    emit('dodaj', zadanie.value)

}


</script>



<template>
<input type="text" v-model="zadanie">
<button @click="przekaz">dodaj</button>
</template>









<style scoped>

</style>