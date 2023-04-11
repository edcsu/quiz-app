<template>
    <div>
        <div class="question-conatiner">
          <h1 class="question">
            What is the chemical value of table salt?
          </h1>
          <div class="answers-container">
            <div class="answer">
              <p class="answer-label">A</p>
              <div class="answer-value">
                <p>NaCl</p>
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
  height: 3rem;
  font-size: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.answer-value {
  background-color: rgb(224, 239, 239);
  width: 100%;
  font-size: 2rem;
  padding: 0 1 rem;
}
</style>
