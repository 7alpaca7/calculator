<script setup lang="ts">
import { onBeforeMount, onMounted, ref } from 'vue';

const panel = ref<HTMLElement | null>(null);
const listBtn = ref<HTMLElement | null>(null);
const listFlag = ref(false);
const listOut = () => {
    listFlag.value = !listFlag.value;
    if (!panel.value)
        return;
    panel.value.style.transform = listFlag.value ? "translateX(0%)" : "translateX(-100%)";
}
const PanelListener = (e: MouseEvent) => {
    const target = e.target as HTMLElement;
    if (!listBtn.value || !panel.value)
        return;
    if (!panel.value.contains(target) && !listBtn.value.contains(target)) {
        listFlag.value = false;
        panel.value.style.transform = "translateX(-100%)";
    }
}
onMounted(() => {
    document.addEventListener("click", PanelListener);
})
onBeforeMount(() => {
    document.removeEventListener("click", PanelListener);
})
</script>
<template>
    <div class="calNav">
        <button ref="listBtn" class="list" @click="listOut"><img src="@/assests/img/list.png" alt="#"></button>
        <div ref="panel" class="test">
            <div>计算器</div>
            <ul>
                <li><img src="@/assests/img/icon.png" alt="#">标准</li>
                <li><img src="@/assests/img/icon.png" alt="#">科学</li>
                <li><img src="@/assests/img/icon.png" alt="#">绘图</li>
                <li><img src="@/assests/img/icon.png" alt="#">程序员</li>
                <li><img src="@/assests/img/icon.png" alt="#">日期计算</li>
            </ul>
            <div>转换器</div>
            <ul>
                <li><img src="@/assests/img/icon.png" alt="#">货币</li>
                <li><img src="@/assests/img/icon.png" alt="#">体积</li>
                <li><img src="@/assests/img/icon.png" alt="#">长度</li>
                <li><img src="@/assests/img/icon.png" alt="#">重量</li>
                <li><img src="@/assests/img/icon.png" alt="#">温度</li>
                <li><img src="@/assests/img/icon.png" alt="#">能量</li>
                <li><img src="@/assests/img/icon.png" alt="#">面积</li>
                <li><img src="@/assests/img/icon.png" alt="#">速度</li>
                <li><img src="@/assests/img/icon.png" alt="#">时间</li>
                <li><img src="@/assests/img/icon.png" alt="#">功率</li>
                <li><img src="@/assests/img/icon.png" alt="#">数据</li>
                <li><img src="@/assests/img/icon.png" alt="#">压强</li>
                <li><img src="@/assests/img/icon.png" alt="#">角度</li>
            </ul>
            <hr>
            <div class="setting">
                <img src="@/assests/img/setting.png" alt="#">设置
            </div>
        </div>
        <p>标准</p>
        <button class="gu"><img src="@/assests/img/guDing.png" alt="#"></button>
        <button class="history"><img src="@/assests/img/history.png"></button>
    </div>
    <div style="clear: both;"></div>
</template>
<style>
.calNav {
    margin-top: 8px;
    height: 10%;
    width: 100%;
}

.calNav button {
    margin-left: 2px;
    margin-right: 1px;
    float: left;
    border: none;
    background-color: #f3f3f3;
    width: 10%;
    outline: none;
    margin-top: 2px;
}

.calNav button:hover {
    background-color: #dcdcdcf6;
}

.calNav button:active {
    background-color: #f3f3f3;
}

.calNav p {
    float: left;
    margin-left: 1%;
    margin-right: 5%;
    text-align: center;
    font-size: 15px;
}

.calNav>button>img {
    margin-top: 1px;
    height: 15px;
    width: 15px;
}

.gu {
    transform: rotate(180deg);
    translate: -40%;
    height: auto;
    scale: 0.9;
}

.history {
    position: absolute;
    right: 0%;
    display: none;
}

.list {
    margin-left: 10px;
    z-index: 10;
    position: relative;
}

.test {
    position: absolute;
    background-color: #f3f3f3;
    top: 0;
    left: 0;
    height: 100%;
    width: 50%;
    transform: translateX(-100%);
    transition: transform 0.3s ease;
    z-index: 9;
    overflow: auto;
    margin-top: 10%;
    padding-left: 2%;
    padding-bottom: 15%;
}

.test ul li {
    list-style: none;
    text-align: left;
    margin: 5% 0 5% 3%;
    height: 10%;
}

.test ul li:hover {
    background-color: #dcdcdcf6;
}
.test ul li:active {
    background-color: #f3f3f3;
}

.test img {
    width: 8%;
    margin: 3% 3% 0 3%;
}
.setting{
    position: relative;
    bottom: 0;
    margin-top: 10%;
}
.setting:hover{
    background-color: #dcdcdcf6;
}
.setting:active{
    background-color: #f3f3f3;
}
</style>