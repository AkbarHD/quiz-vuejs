<script setup>
import QuizContent from '@/components/QuizContent.vue';
import QuizHeader from '@/components/QuizHeader.vue';
import { computed, ref, watch } from 'vue';
import quizes from '../data/quizes.json';
import { useRoute } from 'vue-router';
const router = useRoute(); // fungsi router untuk mengambil id
// console.log(router);
// mengambil id saat ini
const quizId = parseInt(router.params.id);
// console.log(quizId);
const quiz = quizes.find((q) => q.id === quizId);
console.log(quiz);
// console.log(quiz.questions[0]);

 // dinamis halaman nomor pertanyaan
const currentQuestionIndex = ref(0); // utk soal

const questionPage = computed(() => {
    return `${currentQuestionIndex.value + 1} / ${quiz.questions.length}`// ini lebih disarankan dari pada menggunakan watch
});

const barPercentTage = computed(() => {
    // return `${(currentQuestionIndex.value / (quiz.questions.length - 1)) * 100}%`
    return `${((currentQuestionIndex.value + 1) / quiz.questions.length) * 100}%`
});

// const questionPage = ref(`${currentQuestionIndex.value + 1} / ${quiz.questions.length}`); // utk halaman
// watch(
//     () => currentQuestionIndex.value, // gapake juga tidak apa apa
//     () => {
//         questionPage.value = `${currentQuestionIndex.value + 1} / ${quiz.questions.length}`
//     }
// )

</script>
<template>
    <!-- header -->
     <QuizHeader :questionPage="questionPage" :barPercentTage="barPercentTage"/>
    <!-- quiz content -->
     <QuizContent :question="quiz.questions[currentQuestionIndex]"/>
     <button @click="currentQuestionIndex--" :disabled="currentQuestionIndex === 0">Prev</button>
     <button @click="currentQuestionIndex++" :disabled="currentQuestionIndex === quiz.questions.length - 1">Next</button>
</template>

