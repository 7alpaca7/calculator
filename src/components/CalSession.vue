<script setup lang="ts">

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
            <div class="line">
                <button>%</button>
                <button>CE</button>
                <button>C</button>
                <button>del</button>
            </div>
            <div class="line">
                <button><i>1/x</i></button>
                <button>x^2</button>
                <button>&2</button>
                <button>/</button>
            </div>
            <div class="line">
                <button>7</button>
                <button>8</button>
                <button>9</button>
                <button>*</button>
            </div>
            <div class="line">
                <button>4</button>
                <button>5</button>
                <button>6</button>
                <button>-</button>
            </div>
            <div class="line">
                <button>1</button>
                <button>2</button>
                <button>3</button>
                <button>+</button>
            </div>
            <div class="line">
                <button>+/-</button>
                <button>0</button>
                <button>.</button>
                <button class="equal">=</button>
            </div>
        </div>
    </div>
</template>
<style scoped>
.keyBoard{
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-items: center;
    height: 35vh;
    padding-left: 2%;
    padding-bottom: 1%;
}
.keyM{
    display: flex;
    flex-direction: row;
}
.line{
    display: flex;
}
button{
    flex: 1;
    width:100%;
    height: 1.3rem;
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
</style>