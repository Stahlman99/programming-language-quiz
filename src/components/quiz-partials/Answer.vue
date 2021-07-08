<template>
  <div v-for="(answer, index) in answers" :key="index">
    <div :class="cardClass(index)">
      <h3 class="font-bold text-lg">{{answer.text}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Answer',
  props: {
    answers: Array,
    questionIndex: Number
  },
  methods: {
    cardClass(index) {
      let baseClass = "px-4 py-2 mt-12 border border-black rounded-lg ";

      if (index == 0) {
        baseClass += "bg-blue-400"
      } else if (index == 0) {
        baseClass += "bg-red-400"
      } else if (index == 0) {
        baseClass += "bg-green-400"
      } else {
        baseClass += "bg-purple-400"
      }

      return baseClass;
    }
  }
}
</script>

<style scoped>

</style>
