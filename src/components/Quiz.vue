<template>
  <div class="quiz">
    
  </div>
</template>

<script>
export default {
  name: 'Quiz',
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
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
