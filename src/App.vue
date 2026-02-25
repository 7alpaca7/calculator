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
  background-color: #f1f3f9;
  display: flex;
  margin-top: 10%;
}
.left{
  flex:2;
  flex-direction: column;
}
.right{
  flex: 1;
}
</style>
