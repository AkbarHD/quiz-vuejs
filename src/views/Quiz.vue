<script setup>
import QuizContent from '@/components/QuizContent.vue';
import QuizHeader from '@/components/QuizHeader.vue';
import { ref } from 'vue';
import quizes from '../data/quizes.json';
import { useRoute } from 'vue-router';
const router = useRoute(); // fungsi router untuk mengambil id
// console.log(router);
// mengambil id saat ini
const quizId = parseInt(router.params.id);
// console.log(quizId);
const quiz = quizes.find((q) => q.id === quizId);
// console.log(quiz);
// console.log(quiz.questions[0]);

const currentQuestionIndex = ref(0);

</script>
<template>
    <!-- header -->
     <QuizHeader/>
    <!-- quiz content -->
     <QuizContent :question="quiz.questions[currentQuestionIndex]"/>
</template>

