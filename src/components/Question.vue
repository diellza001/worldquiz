<script setup>
import {defineProps, defineEmits} from "vue";

const {question} = defineProps(['question']);
const emit = defineEmits(['selectOption']);

// Funktion, der sender event, når en mulighed vælges.
function emitSelectedOption(isCorrect){
    emit('selectOption', isCorrect);
    
}
</script>

<template>
<div class="text-center mt-5">
    <h1>{{ question.text }}</h1>
    <div class="image-container">
    <img :src="question.img" class="city-image" alt="">
    </div>
            <div class="options-container">
            <div v-for="option in question.options" :key="option.id" class="form-check">
                <input class="form-check-input" type="radio" :name="question.id" :id="option.id" @click="emitSelectedOption(option.isCorrect)">
                <label class="form-check-label" :for="option.id">{{ option.label }}: {{ option.text }}</label>
            </div>
        </div>
</div>
</template>


<style scoped>

.city-image{
    width: 500px;
}
.options-container{
    display: flex;
    justify-content: center; /* Center the radio buttons horizontally */
    gap: 20px;

}

.form-check {
  display: inline-block; /* Make the options appear in a row */
  font-size: 1.5em;
    font-weight: bold;
    margin: 25px;
    padding: 10px;
}

.form-check-input{
    padding: 10px;
    border: none;
    background-color: white;
}

.image-container{
    margin: 20px;

}
</style>

