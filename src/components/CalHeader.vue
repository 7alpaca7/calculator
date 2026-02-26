<script setup lang="ts">
import { computed } from 'vue';
const s = defineModel('str',{type:String,default:''});;
// 自动过滤非数字字符
const displayValue = computed({
  get: () => s.value,
  set: (val: string) => {
    s.value = val.replace(/[^0-9.]/g, '')
  }
})
const a = defineModel('a',{type:String,default:''});
const b = defineModel('b',{type:String,default:''});
const op = defineModel('op',{type:String,default:''});
const equ = defineModel('equ',{type:String,default:''});
const enter = function(){
    console.log(s.value);
}
</script>
<template>
    <div class="result">
        <p class="equation">{{ a }} {{ op }} {{ b }}  {{ equ }}</p>
        <input class="operate" type="text" v-model="displayValue"  @keyup.enter="enter">
    </div>
</template>
<style>
.result{
    height: 20%;
    width: 100%;
    margin-bottom: 1vh;
    padding-right: 5%;
    text-align: right;
}
.equation{
    padding-top: 2%;
    width: 100%;
    height: 40%;
    font-size: 0.7rem;
    color: #9f9f9f;
}
.operate{
    font-size: 2.5rem;
    width: 100%;
    height: 60%;
    border: none;
    outline: none;
    background-color: #f3f3f3;
    text-align: right;
    caret-color: #f3f3f3;
}
</style>