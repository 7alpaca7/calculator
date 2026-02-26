<script setup lang="ts">
import {ref} from 'vue';
const s = ref('')
const test = function(){
    console.log(s.value);
}
</script>
<template>
    <div class="result">
        <p class="equation">72 + 34 =</p>
        <input type="text" class="operate" v-model="s" @keyup.enter="test">
    </div>
</template>
<style scoped>
.result{
    height: 15vh;
    width: 100%;
    margin-bottom: 1vh;
    padding-right: 5%;
    text-align: right;
}
.equation{
    padding-top: 2%;
    font-size: 0.7rem;
    color: #9f9f9f;
}
.operate{
    font-size: 2.5rem;
    border: none;
    outline: none;
    background-color: #f3f3f3;
    text-align: right;
    caret-color: #f3f3f3;
}
</style>