<script setup>
// const props = defineProps(['quiz'])
import { defineProps } from 'vue';
import { useRouter } from 'vue-router';
const { quiz } = defineProps(['quiz'])

const router = useRouter();
// console.log(props);
// console.log(quiz);
// console.log(router);

function goToQuiz() {
  // manggilnya pake name bukan pake path
  router.push({ name: 'quiz', params: { id: quiz.id } });
}
</script>
<template>
        <div class="card" @click="goToQuiz">
            <img :src="quiz.img" :alt="quiz.title">
            <div class="card-body">
              <h2>{{ quiz.title }}</h2>   
              <p>{{ quiz.questions.length }}</p>
            </div>
        </div> 
</template>

<style scoped>

.card{
  width: 270px;
  margin-bottom:20px;
  border-radius:10px;
  overflow: hidden;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.5);
}

.card img{
  width: 100%;
  height: 200px;
  object-fit: cover;
  margin: 0;
}

.card-body{
  padding: 0 10px;
}
</style>