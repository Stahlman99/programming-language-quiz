<template>
  <img class="w-12 h-12 top-1 left-1 absolute" src="../assets/NathanD_Logo.png"/>
  <div class="px-12">
    <div v-if="questionIndex == null">
      <h3 class="font-bold text-xl">What programming language should you start with?</h3>
      <button class="px-4 py-2 font-bold mt-12 border border-black rounded-lg bg-yellow-400" @click="beginQuiz">Begin Quiz</button>
    </div>
    <div v-else>
      <Question :text="questions[questionIndex].text"/>
    </div>
  </div>
</template>

<script>
import Question from './quiz-partials/Question.vue';
import questionInfo from "../data/questions.json";

export default {
  name: 'Quiz',
  components: {
    Question,
  },
  data() {
    return {
      questionIndex: null,
      questions: questionInfo.questions,
    }
  },
  mounted() {
    console.log(this.questions);
  },
  methods: {
    beginQuiz() {
      this.questionIndex = 0;
    }
  }
  
}
</script>

<style scoped>

</style>
