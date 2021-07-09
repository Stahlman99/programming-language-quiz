<template>
  <div>
    <a href="https://twitter.com/_NathanD_"><img class="w-12 h-12 top-2 left-2 absolute" src="../assets/NathanD_Logo.png"/></a>
    <a href="https://twitter.com/_NathanD_"><img class="w-12 h-7 top-3 right-2 absolute" src="../assets/twitter_logo.png"/></a>
    <a href="https://www.youtube.com/channel/UC8NKMRRaBPOiTlUYdMq49sw"><img class="w-12 h-8 top-3 right-16 absolute" src="../assets/youtube_logo.png"/></a>
  </div>
  <div class="px-12">
    <div v-if="questionIndex == null">
      <h3 class="font-bold text-xl mt-24">What programming language should you start with?</h3>
      <button class="px-4 py-2 font-bold mt-12 border border-black rounded-lg bg-yellow-400" @click="beginQuiz">Begin Quiz</button>
    </div>
    <div v-else-if="!completed">
      <Question :text="questions[questionIndex].text"/>
      <Answers :answers="questions[questionIndex].answers" @onClick="nextQuestion($event)"/>
    </div>
    <div v-else>
      <span>Results</span>
    </div>
  </div>
</template>

<script>
import Question from './quiz-partials/Question.vue';
import Answers from './quiz-partials/Answers.vue';
import questionInfo from "../data/questions.json";
import language_data from "../data/language_data.json";

export default {
  name: 'Quiz',
  components: {
    Question,
    Answers
  },
  data() {
    return {
      questionIndex: null,
      questions: questionInfo.questions,
      completed: false,
      languages: language_data.languages,
    }
  },
  methods: {
    beginQuiz() {
      this.questionIndex = 0;
    },
    nextQuestion(points) {
      this.calulatePoints(points);

      this.questionIndex++;

      if(this.questionIndex >= this.questions.length - 1) {
        this.completed = true;
        return;
      }
    },
    calulatePoints(points) {
      this.languages.forEach(language => {
        if(points.includes(language.name)) {
          language.points += 1;
        }
      });
    }
  }
  
}
</script>

<style scoped>

</style>
