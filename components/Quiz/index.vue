<!-- components/Quiz.vue -->
<template>
  <div>
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
            :class="{ 'bg-green-200': isOptionSelected(index) }"
          >
            <input type="radio" :value="index" v-model="selectedAnswer" />
            <div class="font-bold ml-2">{{ option }}</div>
          </label>
        </li>
      </ul>

      <!-- Display the appropriate button based on the current question -->
      <Button @click="checkAnswer">{{
        isLastQuestion ? "Done" : "Next"
      }}</Button>
    </div>
    <div v-else>
      <h2>Quiz Completed!</h2>
      <p>Your score: {{ score }}/3</p>
      <div v-if="score === 3">You are successfully Passed the quize!</div>
      <div v-else>Failed!</div>
      <Button v-if="score !== 3" @click="resetQuiz" class="mr-2"
        >Try Again</Button
      >
    </div>
  </div>
</template>

<script setup>
const questions = [
  {
    question: "What is the capital of France?",
    options: ["Paris", "Berlin", "Madrid", "Rome"],
    correctAnswers: [0],
  },
  {
    question: "Which planet is known as the Red Planet?",
    options: ["Earth", "Mars", "Jupiter", "Venus"],
    correctAnswers: [1],
  },
  {
    question: "What is the largest mammal on Earth?",
    options: ["Elephant", "Blue Whale", "Giraffe", "Hippopotamus"],
    correctAnswers: [1],
  },
];

const currentQuestionIndex = ref(0);
const selectedAnswer = ref(null);
const score = ref(0);

const currentQuestion = ref(questions[currentQuestionIndex.value]);

const checkAnswer = () => {
  const correctAnswers = currentQuestion.value.correctAnswers;

  if (correctAnswers.includes(selectedAnswer.value)) {
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

const resetQuiz = () => {
  currentQuestionIndex.value = 0;
  selectedAnswer.value = null;
  score.value = 0;
  currentQuestion.value = questions[currentQuestionIndex.value];
};

const isLastQuestion = ref(false);

const isOptionSelected = (index) => {
  return selectedAnswer.value === index;
};

watchEffect(() => {
  isLastQuestion.value = currentQuestionIndex.value === questions.length - 1;
});
</script>
