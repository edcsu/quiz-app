<script setup>

const emit = defineEmits(["selectOption"])
 const {question} = defineProps(['question'])

const emitSelectedOption = (isCorrect) => {
  emit("selectOption", isCorrect)
}
</script>

<template>
    <div>
        <div class="question-conatiner">
          <h1 class="question">
            {{ question.text }}
          </h1>
          <div class="answers-container">
            <div v-for="option in question.options" :key="option.id" class="answer" @click="emitSelectedOption(option.isCorrect)">
              <p class="answer-label">{{ option.lable }}</p>
              <div class="answer-value">
                <p>{{ option.text }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
</template>

<style scoped>
.question-conatiner {
  margin-top: 3rem;
}

.question {
  font-size: 1rem;
  margin-bottom: 2rem;
}

.answer {
  display: flex;
  margin-bottom: 2rem;
  cursor: pointer;
}

.answer-label {
  background-color: bisque;
  width: 3rem;
  height: 3.2rem;
  font-size: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.answer-value {
  background-color: rgb(224, 239, 239);
  width: 100%;
  font-size: 2rem;
  padding: 0 1rem;
}
</style>
