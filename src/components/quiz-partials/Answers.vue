<template>
  <div v-for="(answer, index) in answers" :key="index">
    <button :class="cardClass(index)" @click="$emit('onClick', answer.points)">
      <h3 class="font-bold text-lg">{{answer.text}}</h3>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Answers',
  props: {
    answers: Array,
    questionIndex: Number
  },
  methods: {
    cardClass(index) {
      let baseClass = "px-4 py-2 mt-4 border border-black rounded-lg w-full ";

      if (index == 0) {
        baseClass += "bg-blue-400"
      } else if (index == 1) {
        baseClass += "bg-red-400"
      } else if (index == 2) {
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
