<script setup>
    import { RouterLink } from 'vue-router';
    import { defineProps } from 'vue';
    const { quizQuestionsLength, numberCorrectAnswer} = defineProps([
        'quizQuestionsLength', // ini yang dia mbil dari parent
        'numberCorrectAnswer' // ini yang dia mbil dari parent
    ])
</script>
<template>
    <section class="result">
        <p>Score : </p>
        <h1>{{ numberCorrectAnswer }} / {{ quizQuestionsLength }}</h1>
        <RouterLink to="/">Go Back</RouterLink>
    </section>   
</template>

<style scoped>
    .result{
        text-align: center;
        padding: 100px 0;
    }
    p{
        font-size: 25px;
    }

    h1{
        font-size: 80px;
    }
</style>