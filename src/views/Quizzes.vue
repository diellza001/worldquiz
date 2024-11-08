<script setup>
import {ref} from "vue";
import Card from "@/components/Card.vue";
import q from "@/data/quizzes.json";


const quizzes = ref(q);


</script>

<template>
    <h1 class="overskrift text-center mt-5 mb-5">Gæt byer og flag – Tag testen nu!</h1>
        <div class="container">
            <div class="row row-cols-2 mt-3">
                <card v-for="quiz in quizzes" :quiz="quiz" />
            </div>
        </div>
</template>

<style scoped>

.overskrift {
    color: black;
    font-style: italic;
    font-size: 50px;
}
.container{
}
</style>