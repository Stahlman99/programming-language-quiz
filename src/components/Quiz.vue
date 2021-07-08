<template>
  <div class="px-12">
    <h3 class="font-bold text-lg">What programming language should you start with?</h3>
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
