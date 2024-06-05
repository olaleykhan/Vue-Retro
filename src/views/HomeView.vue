<script setup lang="ts">

import {ref} from 'vue'

const fName = ref("Olalekan O.G!!")
const formIsValid = ref(false)

const t = ref({
  name: "Alaf guy",
  nick: "O.G 2 toms",
  skill: "T-shaped. it cannot be described in words."
})

function handleSubmit(e:Event) {
  e.preventDefault()
  console.log(fName.value)
}
function handleToggle() {
  formIsValid.value = !formIsValid.value
}

</script>

<template>
  <main class="main">
   hello world! {{ fName }}
   hello world! {{ t }}

   <form :onsubmit="handleSubmit" >
      <input type="text" v-model="fName" placeholder="Enter your name" />
      <template v-if="formIsValid">
        <button type="submit">Submit</button>
      </template>
   </form>

   <section>
    <!-- clearly form being valid should not be toggles with abutton. lmao.we have input validations for that -->
    <button @click="handleToggle" > {{ formIsValid? "turn off submission": "turn submission back on" }}</button>
   </section>

   <section>
    <div v-bind="t" ></div>
   </section>
   
  </main>
</template>

<style scoped>

.main {
  color: red;
}

</style>
