<script setup lang="ts">
import CalHeader from '@/components/CalHeader.vue';
import CalNav from '@/components/CalNav.vue';
import CalOld from '@/components/CalOld.vue';
import CalSession from '@/components/CalSession.vue';
import { ref } from 'vue';
const str = ref("0");
const a = ref("");
const op = ref("");
const b = ref("");
const equ = ref("");
let bFlag: boolean = false;
let opFlag: boolean = false;
let overFlag: boolean = false;
let zeroFlag: boolean = false;
let resetFlag:boolean = false;
const num = (val: string) => {
  if(resetFlag){
    clear();
    str.value = val;
    return;
  }
  if (bFlag) {
    bFlag = false;
    str.value = val;
    return;
  }
  if (overFlag) {
    overFlag = false;
    zeroFlag = false;
    str.value = val;
    a.value = "";
    op.value = "";
    b.value = "";
    equ.value = "";
    return;
  }
  if (zeroFlag) {
    str.value = val;
    return;
  }

  if (str.value == "0")
    str.value = val;
  else
    str.value += val;
}
const clear = () => {
  str.value = "0";
  a.value = "";
  op.value = "";
  b.value = "";
  equ.value = "";
  bFlag = false;
  opFlag = false;
  overFlag = false;
  zeroFlag = false;
  resetFlag = false;
}
const zero = () => {
  str.value = "0";
  zeroFlag = true;
  if (equ.value != '')
    clear();
}
function isNumeric(s: string) {
  return /^[0-9]+$/.test(s);
}
const point = () => {
  if (!isNumeric(str.value))
    return;
  if (str.value.indexOf(".") == -1) {
    if (equ.value != "") {
      clear();
      str.value = "0."
    } else
      str.value = str.value + ".";
  }
}
const dao = () => {
  if(resetFlag)
    return;
  str.value = 1 / Number(str.value) + "";
}
const ping = () => {
  if(resetFlag)
    return;
  str.value = Number(str.value) ** 2 + "";
}
const sqrt = () => {
  if(resetFlag)
    return;
  str.value = Math.sqrt(Number(str.value)) + "";
}
function fourCal(o: string) {
  if(resetFlag)
    return;
  if (!opFlag) {
    a.value = Number(str.value) + "";
    str.value = Number(str.value) + ""
    b.value = '';
    equ.value = '';
    opFlag = true;
    bFlag = true;
  }
  op.value = o;
  overFlag = false;
}
const yu = () => {
  fourCal("%");
}
const add = () => {
  fourCal("+");
}
const jian = () => {
  fourCal("-");
}
const cheng = () => {
  fourCal("*");
}
const chu = () => {
  fourCal("/");
}
const deng = () => {
  if(resetFlag){
    clear();
    return;
  }
  equ.value = '=';
  if (!opFlag) {
    a.value = Number(str.value) + "";
    return;
  }
  b.value = Number(str.value) + "";
  switch (op.value) {
    case "+": str.value = Number(a.value) + Number(b.value) + ""; break;
    case "-": str.value = Number(a.value) - Number(b.value) + ""; break;
    case "*": str.value = Number(a.value) * Number(b.value) + ""; break;
    case "%": str.value = Number(a.value) % Number(b.value) + ""; break;
    case "/": {
      if(b.value == '0'){
        b.value = '';
        str.value = "除数不能为0";
        resetFlag = true;
      }else{
        str.value = Number(a.value) / Number(b.value) + "";
      }
    }
  }
  opFlag = false;
  overFlag = true;
}
const shan = ()=>{
  if(!isNumeric(str.value) || equ.value!=''){
    clear();
  }
  if(str.value.length!=1){
    str.value = str.value.slice(0,-1);
  }else{
    str.value = "0";
  }
}
</script>
<template>
  <!-- 计算器的容器 -->
  <div class="cal">
    <!-- 左边计算器部分 -->
    <div class="left">
      <CalNav />
      <CalHeader v-model:str="str" v-model:a="a" v-model:b="b" v-model:op="op" v-model:equ="equ" />
      <CalSession @shan="shan" @point="point" @yu="yu" @dao="dao" @ping="ping" @sqrt="sqrt" @zero="zero" @num="num" @clear="clear"
        @add="add" @jian="jian" @cheng="cheng" @chu="chu" @deng="deng" />
    </div>
    <!-- 右边历史记录部分 -->
    <div class="right">
      <CalOld />
    </div>
  </div>
</template>

<style>
@media screen and (max-width:500px) {

  .left {
    flex: 1;
  }

  .right {
    display: none;
    width: 0vw;
  }

  .history {
    display: block;
  }
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-size: 12px;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(192, 192, 192);
}

.cal {
  width: 80vw;
  height: 60vh;
  background-color: #f3f3f3;
  display: flex;
  margin-top: 10%;
  overflow: hidden;
  border-radius: 2%;
  position: relative;
  flex-direction: row;
}

.left {
  width: 50vw;
  height: 60vh;
  display: flex;
  flex-direction: column;
  position: relative;
}

.right {
  width: 30vw;
  height: 60vh;
}
</style>
