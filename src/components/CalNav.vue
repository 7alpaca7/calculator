<script setup lang="ts">

</script>
<template>
    <div class="calNav">
        <button class="list"><img src="@/assests/img/list.png" alt="#"></button>
        <p>标准</p>
        <button class="gu"><img src="@/assests/img/guDing.png" alt="#"></button>
        <button class="history"><img src="@/assests/img/history.png"></button>
    </div>
    <div style="clear: both;"></div>
</template>
<style>
.calNav{
    margin-top: 2%;
    height: 5vh;
    width: 80vw ;
}
.calNav button{
    margin-left: 1%;
    margin-right: 1%;
    float: left;
    border: none;
    background-color: #f3f3f3;
    width: 10%;
    outline: none;
}
.calNav button:hover{
    background-color: #dcdcdcf6;
}
.calNav button:active{
    background-color: #f3f3f3;
}
.calNav p{
    float: left;
    margin-left: 1%;
    margin-right: 5%;
    text-align: center;
    font-size: 15px;
}
.calNav > button > img{
    margin-top: 1%;
    height: 5%;
    width: 40%;
}
.gu{
    transform: rotate(180deg);
    translate: -40%;
    height: auto;
    scale: 0.9;
}
.history{
    position: absolute;
    right: 0%;
    display: none;
}
.list{
    
}
</style>