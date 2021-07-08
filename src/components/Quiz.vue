<template>
  <img class="w-12 h-12 top-1 left-1 absolute" src="../assets/NathanD_Logo.png"/>
  <div class="px-12">
    <h3 v-if="questionIndex == null" class="font-bold text-xl">What programming language should you start with?</h3>
    <Question text="This is not even a question??"/>
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
      questionIndex: null,
    }
  }
  
}
</script>

<style scoped>

</style>
