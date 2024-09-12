<template>
    <div class="result" :class="{wrong:!estaCorreta}">
        <span v-if="estaCorreta">Resposta correta!</span>
        <span v-else>Resposta incorreta!</span>
        <button @click="$emit('proxQuestao')">Próxima questão ➡</button>
    </div>
</template>

<script>
export default {
    props:['estaCorreta']
}
</script>

<style>
    .result {
        height: 400px;
        color: #2c5023;
        width: 70%;
        border-radius: 20px;
        font-size: 5.5rem;

        display: flex;
        flex-direction: column;
        justify-content: center;
        background-color: #5f9253;
    }

    .result hr {
        color: #FFF;
    }

    .result.wrong {
        background-color: #e78a88;
        color: #a33634;
    }

    .result button {
        outline: none;
        align-self: center;
        padding: 10px 20px;
        font-size: 1.7rem;
        border-radius: 8px;
        background-color: #2c5023;
        color: #6f9965;
        font-weight: 600;
        margin-top: 50px;
        cursor: pointer;
        border: none;
    } 

    .result.wrong button {
        background-color: #a33634;
        color: #ffefd5;
    }

    .result button:hover{
        transform: scale(1.1); 
        box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2); 
    }
</style>
