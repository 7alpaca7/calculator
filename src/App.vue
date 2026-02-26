<script setup lang="ts">
import CalHeader from '@/components/CalHeader.vue';
import CalNav from '@/components/CalNav.vue';
import CalOld from '@/components/CalOld.vue';
import CalSession from '@/components/CalSession.vue';

</script>
<template>
  <!-- 计算器的容器 -->
  <div class="cal">
    <!-- 左边计算器部分 -->
      <div class="left">
        <CalNav />
        <CalHeader />
        <CalSession />
      </div>
      <!-- 右边历史记录部分 -->
      <div class="right">
        <CalOld />
      </div>
  </div>
</template>

<style>
@media screen and (max-width:300px) {
  .right{
    display: none;
  }
  .history{
    display: block;
  }
}
* {
   margin: 0;
   padding: 0;
   box-sizing: border-box;
   font-size: 12px;
}
body{
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(192, 192, 192);
}
.cal{
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
.left{
  flex:1;
  display: flex;
  flex-direction: column;
  position: relative;
}
.right{
  flex:1;
}
</style>
