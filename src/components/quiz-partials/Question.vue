<template>
  <div class="flex px-4 py-2 mt-24 mb-10 border border-black rounded-lg bg-yellow-400 w-full md:w-1/2 justify-center">
    <h3 class="font-bold text-lg">{{text}}</h3>
  </div>
</template>

<script>
export default {
  name: 'Question',
  props: {
    text: String,
  }
}
</script>

<style scoped>

</style>
