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
</style>
