<template>
  <div class="px-4 py-2 mt-24 mb-10 border border-black rounded-lg bg-yellow-400">
    <div v-for="(result, index) in results" :key="index">
      <h3 class="font-bold text-lg">{{result.name + ": "}}</h3>
      <p>{{result.desc}}<a :href="result.link ? result.link : ''">{{result.link ? result.link : ''}}</a></p>
      <p></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Results',
  props: {
    results: String,
  }
}
</script>

<style scoped>

</style>
