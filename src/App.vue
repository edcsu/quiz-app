<script setup>
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
      <div v-for="quiz in quizzes" key="quiz.id" class="card">
        <img alt="Math image" class="logo" :src="quiz.img"/>
        <div class="card-text">
          <h2>{{quiz.name}}</h2>
          <p>{{quiz.questions.length}} questions</p>
        </div>
      </div>
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

.card {
  width: 20rem;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 2rem;
  margin-right: 1rem;
  cursor: pointer;
}

.card img {
  width: 100%;
  height: 12rem;
  margin: 0;
}

.card .card-text {
  padding: 0 1rem;
}

.card .card-text h2 {
  font-weight: bold;
}
</style>
