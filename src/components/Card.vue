<script setup>
    import { defineProps } from "vue";
    
    const {quiz} = defineProps(['quiz'])
</script>

<template>
    <div class="card">
        <img alt="Math image" class="logo" :src="quiz.img"/>
        <div class="card-text">
          <h2>{{quiz.name}}</h2>
          <p>{{quiz.questions.length}} questions</p>
        </div>
      </div>
</template>

<style scoped>
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