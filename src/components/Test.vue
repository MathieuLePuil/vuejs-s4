<template>
  <div>
  <button @click="awesome = !awesome">Basculer</button>

  <h1 v-if="awesome">Vue est magnifique!</h1>
  <h1 v-else>Oh non 😢</h1>
  </div>
<!--  <div>-->
<!--    <p>Note 1 : {{ note1 }}-->
<!--      <span v-if="note1 < 8">Inférieure à 8</span>-->
<!--      <span v-else-if="note1 < 10">Inférieure à 10</span>-->
<!--      <span v-else>Supérieure ou égale à 10</span>-->
<!--    </p>-->
<!--    <p>Note 2 : {{ note2 }}-->
<!--      <span v-if="note2 < 10">Inférieure à 10</span>-->
<!--      <span v-else>Supérieure ou égale à 10</span>-->
<!--    </p>-->
<!--    <p>Note 3 : {{ note3 }}-->
<!--      <span v-if="note3 < 10">Inférieure à 10</span>-->
<!--      <span v-else>Supérieure ou égale à 10</span>-->
<!--    </p>-->
<!--    <p>Note 4 : {{ note4 }}-->
<!--      <span v-if="note4 < 10">Inférieure à 10</span>-->
<!--      <span v-else>Supérieure ou égale à 10</span>-->
<!--    </p>-->
<!--    <p>Note 5 : {{ note5 }}-->
<!--      <span v-if="note5 < 10">Inférieure à 10</span>-->
<!--      <span v-else>Supérieure ou égale à 10</span>-->
<!--    </p>-->

<!--    <ul>-->
<!--      <li v-for="(value, key, index) in myObject">-->
<!--        {{ index }}. {{ key }}: {{ value }}-->
<!--      </li>-->
<!--    </ul>-->
<!--  </div>-->

  <ul>
    <li v-for="(value, index) in tableau">
      Note N°{{index + 1}} :
      <span v-if="value < 10" style="color:red">{{ value }} Inférieure à 10</span>
      <span v-else style="color:green">{{value}}</span>
    </li>
  </ul>

</template>

<script setup>
import { ref, computed } from 'vue'

const myObject = {
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
}

let tableau = []

for (let i = 0; i < 10; i++) {
  tableau.push(Math.round(Math.random()*20,0))
}

console.log(tableau)

const note1 = 7
const note2 = 13
const note3 = 7
const note4 = 18
const note5 = 8

const awesome = ref(true)

const somme = computed(() => {
  return note1 + note2 + note3
})



</script>

<style scoped>

</style>
