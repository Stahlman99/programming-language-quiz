<template>
  <div class="px-4 py-4 mt-24 mb-10 border border-black rounded-lg bg-yellow-400 lg:w-1/2">
    <div>
      <h3 class="font-bold text-lg">{{results[0].name + ": "}}</h3>
      <p>{{results[0].desc}} <a class="text-blue-700 font-bold" :href="results[0].link">here</a></p>
      <p></p>
    </div>
    <div class="mt-2">
      <h3 class="font-bold text-lg">{{results[1].name + ": "}}</h3>
      <p>{{results[1].desc}} <a class="text-blue-700 font-bold" :href="results[1].link">here</a></p>
      <p></p>
    </div>
    <div class="mt-2">
      <h3 class="font-bold text-lg">{{results[2].name + ": "}}</h3>
      <p>{{results[2].desc}} <a class="text-blue-700 font-bold" :href="results[2].link">here</a></p>
      <p></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Results',
  props: {
    results: Array,
  }
}
</script>

<style scoped>

</style>
