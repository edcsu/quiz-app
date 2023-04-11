<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="container">
    <header>
      <h1 id="app-text">Quizzes</h1>
      <input id="search-quiz" type="text" placeholder="Search....">
    </header>

    <div class="options-container">
      <div class="card">
        <img alt="Math image" class="logo" src="@/assets/images/math.jpeg"/>
        <div class="card-text">
          <h2>Math</h2>
          <p>15 questions</p>
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
  margin-bottom: 3rem;
  margin-right: 2rem;
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
