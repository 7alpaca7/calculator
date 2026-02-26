<script setup lang="ts">
import CalHeader from '@/components/CalHeader.vue';
import CalNav from '@/components/CalNav.vue';
import CalOld from '@/components/CalOld.vue';
import CalSession from '@/components/CalSession.vue';
import { ref} from 'vue';
const str = ref("0");
const a = ref("");
const op = ref("");
const b = ref("");
const equ = ref("");
let bFlag: boolean = false;
let opFlag: boolean = false;
let overFlag: boolean = false;
const num = (val: string) => {
  if (overFlag) {
    overFlag = false;
    str.value = val;
    a.value = "";
    op.value = "";
    b.value = "";
    equ.value = "";
    return;
  }
  if (bFlag) {
    bFlag = false;
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
}
function fourCal(o: string) {
  if (!opFlag) {
    a.value = str.value;
    b.value = '';
    equ.value = '';
    opFlag = true;
    bFlag = true;
  }
  op.value = o;
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
  equ.value = '=';
  if (!opFlag) {
    a.value = str.value;
    return;
  }
  b.value = str.value;
  switch (op.value) {
    case "+": str.value = Number(a.value) + Number(b.value) + ""; break;
    case "-": str.value = Number(a.value) - Number(b.value) + ""; break;
    case "*": str.value = Number(a.value) * Number(b.value) + ""; break;
    case "/": str.value = Number(a.value) / Number(b.value) + ""; break;
    case "%": str.value = Number(a.value) % Number(b.value) + ""; break;
    case "%": str.value = Number(a.value) + Number(b.value) + ""; break;
    case "%": str.value = Number(a.value) + Number(b.value) + ""; break;
    case "%": str.value = Number(a.value) + Number(b.value) + ""; break;
  }
  opFlag = false;
  overFlag = true;
}
</script>
<template>
  <!-- 计算器的容器 -->
  <div class="cal">
    <!-- 左边计算器部分 -->
    <div class="left">
      <CalNav />
      <CalHeader v-model:str="str" v-model:a="a" v-model:b="b" v-model:op="op" v-model:equ="equ" />
      <CalSession @num="num" @clear="clear" @add="add" @jian="jian" @cheng="cheng" @chu="chu" @deng="deng" />
    </div>
    <!-- 右边历史记录部分 -->
    <div class="right">
      <CalOld />
    </div>
  </div>
</template>

<style>
@media screen and (max-width:300px) {
  .right {
    display: none;
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
  height: 57vh;
  background-color: #f3f3f3;
  display: flex;
  margin-top: 10%;
  overflow: hidden;
  border-radius: 2%;
  position: relative;
  flex-direction: row;
}

.left {
  flex: 1;
  display: flex;
  flex-direction: column;
  position: relative;
}

.right {
  flex: 1;
}
</style>
