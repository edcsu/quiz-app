<script setup>
import { ref } from "vue";
import Question from "../components/Question.vue";
import QuizHeader from "../components/QuizHeader.vue";
import Result from "../components/Result.vue";
import { useRoute } from "vue-router";
import quizzes from "../assets/data/quizzes.json"
import { computed } from "@vue/reactivity";

const route = useRoute()

const quizId = parseInt(route.params.id)

const quiz = quizzes.find(q => q.id == quizId)

const currentQuestionIndex = ref(0)

const questionStatus = computed(() => {
  return `${currentQuestionIndex.value}/${quiz.questions.length}`
})

const barPercentage = computed(() => {
  return `${currentQuestionIndex.value}/${quiz.questions.length * 100}%`
})

const numberOfCorrectAnswers = ref(0)
const onOptionSelected = (isCorrect) => {
  if (isCorrect) {
    numberOfCorrectAnswers++
  }

  if (quiz.questions.length - 1 === currentQuestionIndex.value) {
    showResults.value = true  
  }

  currentQuestionIndex.value++
}
const showResults = ref(false)

</script>

<template>
  <div>
    <QuizHeader :barPercentage="barPercentage" :questionStatus="questionStatus"/>
    <div>
      <Question v-if="!showResults" :question="quiz.questions[currentQuestionIndex]" @selectOption="onOptionSelected" />
      <Result v-else :quizQuestionLength="quiz.questions.length" :numberOfCorrectAnswers="numberOfCorrectAnswers"/>
    </div>
  </div>
</template>

