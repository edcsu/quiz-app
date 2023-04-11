<script setup>
import Card from "./components/Card.vue";
import { RouterLink, RouterView } from 'vue-router'

import q from './assets/data/quizzes.json'
import {ref, watch} from 'vue'

const quizzes = ref(q)
const search = ref("")

watch(search, () => {
  quizzes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLocaleLowerCase()))
})

</script>

<template>
  <div class="container">
    <header>
      <h1 id="app-text">Quizzes</h1>
      <input id="search-quiz" v-model.trim="search" type="text" placeholder="Search....">
    </header>

    <div class="options-container">
      <Card v-for="quiz in quizzes" :key="quiz.id" :quiz="quiz"/>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 1000px;
  margin: 0 auto;
}

header {
  margin-top: 2rem;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
}

#app-text {
  font-weight: bold;
  margin-right: 4rem;
}

#search-quiz {
  border: none;
  background-color: rgba(128, 128, 128, 0.1);
}

.options-container{
  display: flex;
  flex-wrap: wrap;
  margin-top: 2rem;
}
</style>
