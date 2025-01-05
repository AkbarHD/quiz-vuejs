<script setup>
import { defineProps } from 'vue';
const { question } = defineProps(['question']);

// fungsi emit mengirimkan data dari child ke parent
const emit = defineEmits(['selectOption']);
function emitSelectOption(tai) {
    emit('selectOption', tai);
}
</script>
<template>
    <section id="question-container">
        */
    </section>

    <section id="options-container"> <!-- pilih salah satu jawaban -->
        <div class="option" v-for="option in question.answers" :key="option.id" @click="emitSelectOption(option)">
            <p class="option-label">{{ option.label }}</p>
            <div class="option-value">{{ option.text }}</div>
        </div>
    </section>
</template>

<style scoped>
#question-container {
    margin-top: 20px;
}

.question-title {
    font-size: 30px;
    margin-bottom: 20px;
}

.option {
    display: flex;
    align-items: center;
    cursor: pointer;

}

.option-label {
    width: 50px;
    height: 50px;
    background-color: #53d862;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    font-size: 20px;
    border-radius: 5px;
}

.option-value {
    font-size: 20px;
    font-weight: bold;
    padding: 0 20px;
    background-color: #e2e2e2;
    display: flex;
    align-items: center;
    width: 100%;
    height: 50px;
}
</style>