<script setup>
import QuizContent from '@/components/QuizContent.vue';
import QuizHeader from '@/components/QuizHeader.vue';
import { ref, watch } from 'vue';
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

// dinamis halaman nomor pertanyaan
const currentQuestionIndex = ref(0);
const questionPage = ref(`${currentQuestionIndex.value + 1} / ${quiz.questions.length}`);
watch(
    () => currentQuestionIndex.value,
    () => {
        questionPage.value = `${currentQuestionIndex.value + 1} / ${quiz.questions.length}`
    }
)

</script>
<template>
    <!-- header -->
     <QuizHeader :questionPage="questionPage"/>
    <!-- quiz content -->
     <QuizContent :question="quiz.questions[currentQuestionIndex]"/>
     <button @click="currentQuestionIndex++" :disabled="currentQuestionIndex === quiz.questions.length - 1">Next</button>
</template>

