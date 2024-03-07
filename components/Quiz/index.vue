<!-- components/Quiz.vue -->
<template>
  <div>
    <div v-if="currentQuestion">
      <h2>{{ currentQuestion.question }}</h2>
      <ul>
        <li v-for="(option, index) in currentQuestion.options" :key="index">
          <label
            class="flex mt-4 border p-2 mb-4"
            :class="{ 'bg-green-200': isOptionSelected(option) }"
          >
            <input type="radio" :value="option" v-model="selectedAnswer" />
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

      <!-- Display the appropriate button based on the score -->
      <Button v-if="score === 3" class="mr-2">Done</Button>
      <Button v-else @click="resetQuiz">Try Again</Button>
    </div>

    <!-- Display the current question index -->
    <div class="font-bold text-2xl ml-10">
      {{ currentQuestionIndex + 1 }}/ {{ questions.length }}
    </div>
  </div>
</template>

<script setup>
const questions = [
  {
    question: "What is the capital of France?",
    options: ["Paris", "Berlin", "Madrid", "Rome"],
    correctAnswer: 0,
  },
  {
    question: "Which planet is known as the Red Planet?",
    options: ["Earth", "Mars", "Jupiter", "Venus"],
    correctAnswer: 1,
  },
  {
    question: "What is the largest mammal on Earth?",
    options: ["Elephant", "Blue Whale", "Giraffe", "Hippopotamus"],
    correctAnswer: 1,
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

const isOptionSelected = (option) => {
  return selectedAnswer.value === option;
};

// Watch for changes in currentQuestionIndex and update isLastQuestion accordingly
watchEffect(() => {
  isLastQuestion.value = currentQuestionIndex.value === questions.length - 1;
});
</script>
