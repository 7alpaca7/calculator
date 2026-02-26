<script setup lang="ts">
const emit = defineEmits(['point','zero','num','clear','add','jian','cheng','chu','yu','dao','ping','sqrt','deng']);
const press = (val:number)=>{
    emit("num",""+val);
}
const clear = ()=>{
    emit('clear');
}
const add = ()=>{
    emit('add');
}
const jian = ()=>{
    emit('jian');
}
const cheng = ()=>{
    emit('cheng');
}
const chu = ()=>{
    emit('chu');
}
const deng = ()=>{
    emit('deng');
}
const yu = ()=>{
    emit('yu');
}
const dao = ()=>{
    emit('dao');
}
const ping = ()=>{
    emit('ping');
}
const sqrt = ()=>{
    emit('sqrt');
}
const zero = ()=>{
    emit('zero');
}
const point = ()=>{
    emit('point');
}
</script>
<template >
    <div class="keyBoard">
        <div class="keyM">
            <button>MC</button>
            <button>MR</button>
            <button>M+</button>
            <button>M-</button>
            <button>MS</button>
        </div>
        <div class="keyN">
                <button @click="yu()">%</button>
                <button @click="zero()">CE</button>
                <button @click="clear()">C</button>
                <button><img src="@/assests/img/delete.png" alt=""></button>
                <button @click="dao()"><i>1/x</i></button>
                <button @click="ping()"><math xmlns="http://www.w3.org/1998/Math/MathML">
                        <msup>
                            <mi>x</mi>
                            <mn>2</mn>
                        </msup>
                    </math></button>
                <button @click="sqrt()">
                    <math xmlns="http://www.w3.org/1998/Math/MathML">
                        <mroot>
                            <mi>x</mi>
                            <mn>2</mn>
                        </mroot>
                    </math>
                </button>
                <button @click="chu()">÷</button>
                <button @click="press(7)">7</button>
                <button @click="press(8)">8</button>
                <button @click="press(9)">9</button>
                <button @click="cheng()">×</button>
                <button @click="press(4)">4</button>
                <button @click="press(5)">5</button>
                <button @click="press(6)">6</button>
                <button @click="jian()">-</button>
                <button @click="press(1)">1</button>
                <button @click="press(2)">2</button>
                <button @click="press(3)">3</button>
                <button @click="add()">+</button>
                <button>+/-</button>
                <button @click="press(0)">0</button>
                <button @click="point()">.</button>
                <button class="equal" @click="deng()">=</button>
        </div>
    </div>
</template>
<style>
.keyBoard{
    display: flex;
    width: 100%;
    height: 50%;
    min-height: 0;
    flex-direction: column;
    /* align-content: center;
    justify-items: center; */
    align-content: start;
    padding-left: 2%;
    padding-bottom: 1%;
    margin-top: auto;
    margin-bottom: 5%;
}
.keyM{
    display: flex;
    flex-direction: row;
}
.keyN{
    display: grid;
    grid-template-columns: repeat(4,1fr);
}
button{
    flex: 1;
    height: 1.5rem;
    font-size: 13px;
    border-radius: 4px;
    background-color: #ffffff;
    margin: 0 0.2rem 0.2rem 0;
    font-size: 0.7rem;
    border: none;
    text-align: center;
}
button:hover{
    background-color: #dcdcdcf6;
}
button:active{
    background-color: #ffffff;
}
.keyM button{
    background-color: #f3f3f3;
    
}
.keyM button:hover{
    background-color: #dcdcdcf6;
}
.equal{
    background-color: #09385c;
    color: #fff;
}
.equal:hover{
    background-color: #0d4d7e;
}
.equal:active{
    background-color: #09385c;
}
.keyN button img{
    height: 100%;
    /* width: auto; */
}
</style>