<!-- components/Quiz.vue -->
<template>
  <div v-if="currentQuestion">
    <div class="flex-col items-center">
      <div class="font-light text-end">
        {{ currentQuestionIndex + 1 }} / {{ questions.length }}
      </div>
      <div class="font-bold">{{ currentQuestion.question }}</div>
    </div>
    <ul>
      <li v-for="(option, index) in currentQuestion.options" :key="index">
        <label
          class="flex mt-4 border p-2 mb-4"
          :class="{ 'bg-green-200': selectedAnswer === option }"
        >
          <input type="radio" :value="option" v-model="selectedAnswer" />
          <div class="font-bold ml-2">{{ option }}</div>
        </label>
      </li>
    </ul>
    <Button @click="checkAnswer">Next</Button>
  </div>
  <div v-else>
    <div class="font-bold text-2xl">Quiz Completed!</div>
    <p class="font-bold text-2xl">Your score: {{ score }}/3</p>
    <div class="mt-10">
      <Button v-if="score === 3">Done</Button>
      <Button v-else>Try Again</Button>
    </div>
  </div>
</template>

<script setup>
const questions = [
  {
    question: "What is the capital of France?",
    options: ["Paris", "Berlin", "Madrid", "Rome"],
    correctAnswer: "Paris",
  },
  {
    question: "Which planet is known as the Red Planet?",
    options: ["Earth", "Mars", "Jupiter", "Venus"],
    correctAnswer: "Mars",
  },
  {
    question: "What is the largest mammal on Earth?",
    options: ["Elephant", "Blue Whale", "Giraffe", "Hippopotamus"],
    correctAnswer: "Blue Whale",
  },
];

const currentQuestionIndex = ref(0);
const selectedAnswer = ref(null);
const score = ref(0);

const currentQuestion = ref(questions[currentQuestionIndex.value]);

const checkAnswer = () => {
  if (selectedAnswer.value === currentQuestion.value.correctAnswer) {
    score.value++;
  }

  if (currentQuestionIndex.value < questions.length - 1) {
    currentQuestionIndex.value++;
    selectedAnswer.value = null;
    currentQuestion.value = questions[currentQuestionIndex.value];
  } else {
    currentQuestion.value = null;
  }
};
</script>
