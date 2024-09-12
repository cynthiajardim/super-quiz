<template>
    <div class="question">
        <span>{{questao.text}}</span>
        <ul class="answers">
            <li v-for="(resposta, i) in questao.answers" :key="resposta">
                <!-- <span class="number"> {{ i+1 }} </span> -->
                <span class="text"> {{ resposta.text }} </span>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props:['questao']
}
</script>

<style>
    .question {
        height: 400px;
        color: #000;
        background-color: #f1c885;
        width: 70%;
        border-radius: 20px;
        font-size: 2.5rem;

        display: flex;
        flex-direction: column;
        justify-content: space-around;
    }

    ul.answers {
        font-size: 2rem;
        padding: 0;
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
    }

    .answers li {
        padding: 10px;
        margin: 20px;
        background-color: #b5873b;
        border-radius: 8px;
        width: 40%;

        display: flex;
        cursor: pointer;
    }

    .answers .number {
        padding: 10px;
        background-color: #b5873b;
        color: #FFF;
        flex-basis: 30px;
        border-top-left-radius: 8px;
        border-bottom-left-radius: 8px;
    }

    .answers .text {
        flex: 1;
        align-self: center;
    }
</style>
