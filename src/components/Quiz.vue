<template>
  <img class="w-12 h-12 top-3 left-1 absolute" src="../assets/NathanD_Logo.png"/>
  <div class="px-12">
    <h3 v-if="questionIndex == 0" class="font-bold text-lg">What programming language should you start with?</h3>
    <Question :question="{text: 'This is not even a question??'}"/>
  </div>
</template>

<script>
import Question from './quiz-partials/Question.vue'

export default {
  name: 'Quiz',
  components: {
    Question,
  },
  data() {
    return {
      questionIndex: 1,
      paths: [
        'Web Developer',
        'Software Engineer',
        'Game Developer',
        'Mobile Developer',
        'Machine learning / AI Engineer',
        'Database Manager'
      ],
      languages: [
        'JavaScript',
        'Python',
        'Ruby',
        'C',
        'C++',
        'Java',
        'Flutter',
        'SQL',
      ],
    }
  }
  
}
</script>

<style scoped>

</style>
