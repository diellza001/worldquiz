<script setup>
import {defineProps} from "vue";
import {RouterLink} from "vue-router";

const {quizQuestionLength, numberOfCorrectAnswers} = defineProps(['quizQuestionLength', 'numberOfCorrectAnswers']);


</script>

<template>

<div class="row mt-5">
    <div class="text-center">
        <h3 class="results mt-5"> Her er dit resultat</h3>
        <h2 class="svar">Du fik {{numberOfCorrectAnswers}} ud af {{quizQuestionLength}} svar korrekte</h2>
        <h1 class="besked"> {{
                numberOfCorrectAnswers === 10
                    ? "🎉 Du klarede det! 🎉"
                    : numberOfCorrectAnswers >= 7
                        ? "Du var der næsten! 😩"
                        : "Prøv igen! 😕"
            }}
        </h1>
        <Router-link class="btn mt-3"  to="/">Tilbage</Router-link>
    </div>
</div>
</template>

<style scoped>

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

.results{
    font-size: 2em;
    color: black;

}
.svar{
    color: black;

}
.besked{
    font-size: 3em;
    color: black;
    font-weight: bold;
}

</style>