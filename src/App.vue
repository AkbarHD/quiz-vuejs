<script setup>
import { ref, watch } from 'vue';
import srcQuiz from './data/quizes.json'
import QuizCard from './components/QuizCard.vue'

const quizes = ref(srcQuiz)
// console.log(quizes);

const search = ref('')
watch(search, () => {
  quizes.value = srcQuiz.filter((quiz) => {
    return quiz.title.toLowerCase().includes(search.value.toLowerCase())
  });
});
</script>
<template>
  <main>
    <header>
      <h1 id="title">Quiz</h1>
      <input v-model="search" type="text" id="search-input">
    </header>

    <section id="quiz-container">
      <!-- <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img :src="quiz.img" :alt="quiz.title">
        <div class="card-body">
          <h2>{{ quiz.title }}</h2>
          <p>{{ quiz.questions.length }} questions</p>
        </div>
      </div> -->
      <!-- v-bind="quiz" sama saja dengan :quiz="quiz" -->
      <QuizCard v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
    </section>
  </main>
</template>

<style scoped>
main{
  max-width: 900px;
  margin: 0 auto;
}
header{
  display: flex;
  align-items: center;
  gap: 50px;
}

#title{
  font-weight: bold;
  font-size: 36px;
}

#search-input{
  border: none;
  background-color: gray;
  padding: 10px;
  border-radius: 5px;
   color: white;
}

#quiz-container{
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  margin-top:20px;
}
</style>