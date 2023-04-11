<script setup>
import {RouterLink} from 'vue-router';
const {numberOfCorrectAnswers, quizQuestionLength} = defineProps(["numberOfCorrectAnswers", "quizQuestionLength"])
</script>

<template>
    <div class="results">
        <p id="result-text">Your results...</p>
        <h1 id="result">{{numberOfCorrectAnswers}}/{{quizQuestionLength}}</h1>
    </div>
    <RouterLink to="/">Go Back</RouterLink>
</template>

<style scoped>
.results {
    text-align: center;
    padding: 5rem 0;
}

#result-text {
    font-size: 5rem;
}

#result {
    font-size: 10rem;
}

</style>