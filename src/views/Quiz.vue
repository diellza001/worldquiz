<script setup>
import quizzes from "@/data/Quizzes.json";
import {useRoute} from "vue-router";
import Question from "@/components/Question.vue";
import Result from "@/components/Result.vue";
import {ref} from "vue";


const route = useRoute();
const quizId = parseInt(route.params.id);
const quiz = quizzes.find(q => q.id === quizId);
const currentQuestionIndex = ref(0);
const numberOfCorrectAnswers = ref(0);
const showResults = ref(false);

function onOptionSelected(isCorrect){
    if(isCorrect){
        numberOfCorrectAnswers.value++;

    }

    if (quiz.questions.length - 1 === currentQuestionIndex.value){
        showResults.value = true;

    }

    currentQuestionIndex.value++;
}
</script>

<template>
    <div class="container">
        <div class="mt-3">
            <Question
                v-if="!showResults"
                :question ="quiz.questions[currentQuestionIndex]"
            @select-option="onOptionSelected"
            />
            <Result
                v-else
                :quizQuestionLength="quiz.questions.length"
                :numberOfCorrectAnswers="numberOfCorrectAnswers"
            />
        </div>

    </div>

</template>

<style scoped>

</style>