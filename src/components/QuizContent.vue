<template>
      <section id="question-container">
        <h1 class="question-title">what is 1 + 1?</h1>
    </section>

    <section id="options-container">
         <div class="option">
            <p class="option-label">A.</p>
            <div class="option-value">1</div>
        </div>
        <div class="option">
            <p class="option-label">B.</p>
            <div class="option-value">2</div>
        </div>
        <div class="option">
            <p class="option-label">C.</p>
            <div class="option-value">3</div>
        </div>
    </section>
</template>

<style scoped>
     #question-container{
        margin-top: 20px;
    }

    .question-title{
        font-size: 30px;
        margin-bottom: 20px;
    }

    .option{
        display: flex;
        align-items: center;
        cursor: pointer;

    }
    .option-label{
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

    .option-value{
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