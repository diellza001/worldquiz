<script setup>
import {defineProps} from "vue";

const {quiz} = defineProps(["quiz"]);


</script>

<template>
    <div class="container">
        <div class="card rounded-4">
            <img :src="quiz.img" class="card-img-top object-fit-cover rounded-3" alt="">
            <div class="card-body text-center">
                <h5 class="card-title">{{ quiz.name }}</h5>
                <p class="card-text">Antal spørgsmål: {{ quiz.questions.length }}</p>
                <p class="card-text"> {{ quiz.description }}</p>
                <RouterLink :to="'/quiz/'+ quiz.id" class="btn">Start Quiz</RouterLink>
            </div>
        </div>
    </div>
</template>

<style scoped>

.card-img-top{
    height: 160px;
    margin-bottom: 15px;

}

.btn{
    background-color: #487c8f;
    box-shadow: 4px 4px 2px rgba(0, 0, 0, 0.5);
    font-weight: bold;
    padding: 12px 20px;
    color: white;
    margin-top: 15px;
}
.btn:hover{
    background-color: #78bad2;
    color: white;
}

.card {
    padding: 10px;
    width: 480px;
    height: 400px;
    background-color: white;
    box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.7);
}

.container {
    display: flex;
    justify-content: center; /* Centrerer vandret */
    align-items: center; /* Centrerer lodret */
}





</style>