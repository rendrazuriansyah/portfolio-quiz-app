<script setup>
import QuizHeader from "@/components/QuizHeader.vue";
import QuizContent from "@/components/QuizContent.vue";
import { computed, ref } from "vue";
import { useRoute } from "vue-router";
import quizes from "../data/quizes.json";

const route = useRoute();
const quizId = parseInt(route.params.id);
const quiz = quizes.find((quiz) => quiz.id === quizId);
const currentQuestionIndex = ref(0);
const questionPage = computed(() => {
	const totalQuestions = quiz.questions.length;
	const currentPage = currentQuestionIndex.value + 1;
	return `${
		currentPage > totalQuestions ? totalQuestions : currentPage
	} / ${totalQuestions}`;
});
const barPercentage = computed(() => {
	const totalQuestions = quiz.questions.length;
	const currentPage = currentQuestionIndex.value + 1;
	const percentage = ((currentPage / totalQuestions) * 100).toFixed(2);
	return `${percentage > 100 ? 100 : percentage}%`;
});
const numberOfCorrectAnswers = ref(0);

function onSelectOption(option) {
	if (option.correct) {
		numberOfCorrectAnswers.value++;
	}
	currentQuestionIndex.value++;
}
</script>

<template>
	<QuizHeader :questionPage="questionPage" :barPercentage="barPercentage" />
	<QuizContent
		:question="quiz.questions[currentQuestionIndex]"
		@selectOption="onSelectOption"
	/>
	<button
		@click="currentQuestionIndex++"
		:disabled="currentQuestionIndex === quiz.questions.length - 1"
	>
		Next
	</button>
</template>

<style scoped></style>
