<template>
	<div id="app">
		<h1>Quiz</h1>
		<Question :questao="questoes[numQuestao]" v-if="exibindoQuestao"></Question>
		<Result v-else :estaCorreta="escolha"></Result>
	</div>
</template>

<script>
import Question from './components/Question.vue';
import questions from './util/questions'
import Result from './components/Result.vue';

export default {
	data(){
		return {
			numQuestao: this.geraNumQuestaoAleat(),
			questoes: questions,
			exibindoQuestao: true,
			escolha: ''
		}
	},	
	components: {
		Question,
		Result
	},
	methods:{
		geraNumQuestaoAleat(){
			return Math.floor(Math.random() * 11)
		}
	}
}
</script>

<style>
body {
	background: linear-gradient(to right, #ffefd5, #fff8dc);
	color: #cd853f;
	height: 100vh;
}

#app {
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;

	display: flex;
	flex-direction: column;
	align-items: center;
}

#app h1 {
	font-weight: 200;
	font-size: 4rem;
}

@keyframes flip-out {
	from { transform: rotateY(0deg); }
	to { transform: rotateY(90deg); }
}

@keyframes flip-in {
	from { transform: rotateY(90deg); }
	to { transform: rotateY(0deg); }
}

.flip-enter-active {
	animation: flip-in 0.3s ease;
}

.flip-leave-active {
	animation: flip-out 0.3s ease;
}
</style>
