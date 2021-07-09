<template>
  <div class="md:border md:rounded-lg md:border-black">
    <a href="https://twitter.com/_NathanD_"><img class="w-12 h-12 top-1 left-2 absolute" src="../assets/NathanD_Logo.png"/></a>
    <a href="https://twitter.com/_NathanD_"><img class="w-12 h-7 top-3 right-2 absolute" src="../assets/twitter_logo.png"/></a>
    <a href="https://www.youtube.com/channel/UC8NKMRRaBPOiTlUYdMq49sw"><img class="w-12 h-8 top-3 right-16 absolute" src="../assets/youtube_logo.png"/></a>
  </div>
  <div class="px-12">
    <div v-if="questionIndex == null && !finalResults">
      <h3 class="font-bold text-xl mt-24">What programming language should you learn?</h3>
      <button class="px-4 py-2 font-bold mt-12 border border-black rounded-lg bg-yellow-400" @click="beginQuiz">Begin Quiz</button>
    </div>
    <div class="flex flex-col items-center" v-else-if="!finished">
      <Question :text="questions[questionIndex].text"/>
      <Answers :answers="questions[questionIndex].answers" @onClick="nextQuestion($event)"/>
    </div>
    <div class="flex justify-center" v-else>
      <Results :results="finalResults"/>
    </div>
  </div>
</template>

<script>
import Question from './quiz-partials/Question.vue';
import Answers from './quiz-partials/Answers.vue';
import Results from './quiz-partials/Results.vue';
import questionInfo from "../data/questions.json";
import language_data from "../data/language_data.json";

export default {
  name: 'Quiz',
  components: {
    Question,
    Answers,
    Results
  },
  data() {
    return {
      languages: language_data.languages,
      questions: questionInfo.questions,
      questionIndex: null,
      finished: false,
      finalResults: null,
    }
  },
  methods: {
    beginQuiz() {
      this.questionIndex = 0;
    },
    nextQuestion(points) {
      this.calulatePoints(points);

      if(this.questionIndex >= this.questions.length - 2) {
        this.finished = true;
        this.endQuiz();
      } else {
        this.questionIndex++;
      }
    },
    calulatePoints(points) {
      this.languages.forEach(language => {
        if(points.includes(language.name)) {
          language.points += this.questions[this.questionIndex].weight;
        }
      });
    },
    endQuiz() {
      this.questionIndex = null;
      this.languages.sort((a, b) => {
        if (a.points == b.points) {
          return 0;
        } else {
          return b.points - a.points;
        }
      })

      this.finalResults = [this.languages[0], this.languages[1], this.languages[2]];
    }
  }
  
}
</script>

<style scoped>

</style>
