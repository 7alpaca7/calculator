<script setup lang="ts">
import { ref } from 'vue';

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
</script>
<template>
    <div class="oldNav">
        <span ref="one" @click="clickNav($event)">历史记录</span>
        <span ref="two" @click="clickNav($event)">记忆</span>
    </div>
    <div class="oldAll">

    </div>
</template>
<style scoped>
.oldNav {
    display: flex;
    flex-direction: row;
    padding-top: 5%;
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
</style>