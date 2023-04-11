<script setup>

const { barPercentage, questionStatus } = defineProps(["barPercentage", "questionStatus"])
</script>

<template>
  <header>
    <h2>Question {{ questionStatus }}</h2>
    <div class="bar">
      <div class="completion" :style="{width: barPercentage}"></div>
    </div>
  </header>
</template>


<style scoped>
header {
  margin-top: 3rem;
}

.bar {
  width: 18rem;
  height: 4rem;
  border: 0.4rem solid bisque;
}

.completion {
  height: 100%;
  width: 0%;
  background-color: bisque;
}
</style>