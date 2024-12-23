<script setup>
    import { defineProps } from 'vue';
const { questionPage, barPercentTage } = defineProps([
    'questionPage',
    'barPercentTage'
]);
</script>
<template>
    <header>
        <h4>Question {{ questionPage }}</h4>
        <div class="bar">
            <div class="bar-progress" :style="{ width: barPercentTage}"></div>
        </div>
    </header>
</template>

<style scoped>
     header{
        margin-top: 20px;
    }
    header h4{
        font-size: 30px;
    }

    header .bar{
        width: 100%;
        height: 50px;
        border: 3px solid #adf7b6;
    }

    header .bar .bar-progress{
        width: 0%;
        height: 100%;
        background-color: #adf7b6;
    }
</style>
