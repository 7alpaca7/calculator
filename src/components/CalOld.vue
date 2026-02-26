<script setup lang="ts">
import { ref, watch } from 'vue';
interface record{
    equation:String,
    result:String
}
const history = ref<record[]>([]);
const a = defineModel('a',{type:String,default:""});
const b = defineModel('b',{type:String,default:""});
const op = defineModel('op',{type:String,default:""});
const equ = defineModel('equ',{type:String,default:""});
const str = defineModel('str',{type:String,default:""});
const one = ref<HTMLElement | null>(null);
const two = ref<HTMLElement | null>(null);
const clickNav = (e: Event) => {
    const tar = e.target as HTMLElement;
    if (!one.value || !two.value) return;
    if (tar.innerText == '历史记录') {
        one.value.style.textDecoration = "underline blue 1px solid";
        two.value.style.textDecoration = "none";
    } else {
        one.value.style.textDecoration = "none";
        two.value.style.textDecoration = "underline blue 1px solid";
    }
}
watch(equ,()=>{
    if(equ.value != '=')
        return;
    history.value.push({
        equation:a.value+' '+op.value+''+b.value+' =',
        result:str.value
    })
})
</script>
<template>
    <div class="oldNav">
        <span ref="one" @click="clickNav($event)" style="text-decoration: underline blue 1px solid;">历史记录</span>
        <span ref="two" @click="clickNav($event)">记忆</span>
    </div>
    <div class="oldAll">
        <div class="content" v-for="item,index in history.slice().reverse()" :key="index">
            <p>{{ item.equation }}</p>
            <p>{{ item.result }}</p>
        </div>
    </div>
</template>
<style scoped>
.oldNav {
    display: flex;
    flex-direction: row;
    padding-top: 5%;
    padding-left: 5%;
    width: 30vw;
}

.oldNav span {
    flex: 1;
    margin-right: 5%;
    text-underline-offset: 5px;
    transform: 0.2s;
}

.oldAll {
    margin-top: 10%;
    display: flex;
    position: relative;
    font-weight: bold;
    flex-direction: column;
    overflow-y: auto;
    height: 45vh;
    width: 100%;
    text-align: right;
    padding-right: 15%;
}
.content{
    margin-bottom: 2%;
    width: 100%;
}
.content p{
    padding-right: 5%;
}
.content:hover{
    background-color: #dcdcdcf6;
}
.content:active{
    background-color: #f3f3f3;
}
</style>