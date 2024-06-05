<script setup lang="ts">

import {ref} from 'vue'

const fName = ref("Olalekan O.G!!")
const formIsValid = ref()

function handleSubmit(e:Event) {
  e.preventDefault()
  console.log(fName.value)
}

</script>

<template>
  <main class="main">
   hello world! {{ fName }}

   <form :onsubmit="handleSubmit" >
      <input type="text" v-model="fName" placeholder="Enter your name" />
      <button :disabled="formIsValid" >Submit</button>
   </form>
   
  </main>
</template>

<style scoped>

.main {
  color: red;
}

</style>
