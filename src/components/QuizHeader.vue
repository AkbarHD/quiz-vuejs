<template>
    <header>
        <h4>Question 1</h4>
        <div class="bar">
            <div class="bar-progress"></div>
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
        width: 50%;
        height: 100%;
        background-color: #adf7b6;
    }
</style>
