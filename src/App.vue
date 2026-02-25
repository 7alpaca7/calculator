<script setup lang="ts">
import CalHeader from '@/components/CalHeader.vue';
import CalNav from '@/components/CalNav.vue';
import CalOld from '@/components/CalOld.vue';
import CalSession from '@/components/CalSession.vue';

</script>
<template>
  <!-- 计算器的容器 -->
  <div class="cal">
      <div class="left">
        <CalNav />
        <CalHeader />
        <CalSession />
      </div>
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
  background-color: rgb(225, 225, 225);
}
.cal{
  width: 80vw;
  height: 57vh;
  background-color: red;
  display: flex;
  margin-top: 10%;
}
.left{
  flex:1;
  background-color: blue;
  flex-direction: column;
}
.right{
  flex: 1;
}
</style>
