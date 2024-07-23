<script setup>
import { defineProps } from "vue";

const { question } = defineProps(["question"]);
</script>

<template>
	<section id="question-container">
		<h1 class="question-title">{{ question.text }}</h1>
	</section>
	<section id="options-container">
		<div class="option" v-for="option in question.answers" :key="option.id">
			<p class="option-label">{{ option.label }}.</p>
			<div class="option-value">{{ option.text }}</div>
		</div>
	</section>
</template>

<style scoped>
#question-container {
	margin: 40px 0;
}

.question-title {
	font-size: 32px;
	font-weight: bold;
	color: #343a40;
}

.option {
	display: flex;
	align-items: center;
	cursor: pointer;
}

.option-label,
.option-value {
	transition: background-color 0.2s ease-in-out;
}

.option:hover .option-label,
.option:hover .option-value {
	background-color: #ffc107;
	border: 5px solid transparent;
}

.option-label {
	font-size: 24px;
	font-weight: bold;
	width: 60px;
	height: 50px;
	background-color: #f8ad54;
	display: flex;
	align-items: center;
	justify-content: center;
	border-radius: 10px 0 0 10px;
}

.option-value {
	font-size: 24px;
	font-weight: bold;
	padding: 0 20px;
	background-color: #e9ecef;
	width: 100%;
	height: 50px;
	display: flex;
	align-items: center;
	border-radius: 0 10px 10px 0;
}
</style>
