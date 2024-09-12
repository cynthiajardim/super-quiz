<template>
    <div class="question">
        <span>{{questao.text}}</span>
        <ul class="answers">
            <li v-for="resposta in questao.answers" :key="resposta" @click="$emit('respostaEscolhida', resposta.correct)">
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

    .answers li:hover{
        transform: scale(1.1); 
        box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2); 
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
