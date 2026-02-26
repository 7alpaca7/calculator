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
                <button>÷</button>
                <button>CE</button>
                <button>C</button>
                <button><img src="@/assests/img/delete.png" alt=""></button>
                <button><i>1/x</i></button>
                <button><math xmlns="http://www.w3.org/1998/Math/MathML">
                        <msup>
                            <mi>x</mi>
                            <mn>2</mn>
                        </msup>
                    </math></button>
                <button>
                    <math xmlns="http://www.w3.org/1998/Math/MathML">
                        <mroot>
                            <mi>x</mi>
                            <mn>2</mn>
                        </mroot>
                    </math>
                </button>
                <button>/</button>
                <button>7</button>
                <button>8</button>
                <button>9</button>
                <button>×</button>
                <button>4</button>
                <button>5</button>
                <button>6</button>
                <button>-</button>
                <button>1</button>
                <button>2</button>
                <button>3</button>
                <button>+</button>
                <button>+/-</button>
                <button>0</button>
                <button>.</button>
                <button class="equal">=</button>
        </div>
    </div>
</template>
<style scoped>
.keyBoard{
    display: flex;
    flex: 1;
    min-height: 0;
    flex-direction: column;
    align-content: center;
    justify-items: center;
    padding-left: 2%;
    padding-bottom: 1%;
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
    width: auto;
}
</style>