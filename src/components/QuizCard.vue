<script setup>
import { defineProps } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const { quiz } = defineProps(["quiz"]);

function goToQuiz() {
	router.push({ name: "quiz", params: { id: quiz.id } });
}
</script>

<template>
	<div class="card" @click="goToQuiz">
		<img :src="quiz.img" :alt="quiz.title" />
		<div class="card-body">
			<h2>{{ quiz.title }}</h2>
			<p>{{ quiz.questions.length }} Questions</p>
		</div>
	</div>
</template>

<style scoped>
.card {
	width: 270px;
	margin-right: 30px;
	margin-bottom: 30px;
	border-radius: 5px;
	overflow: hidden;
	box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
	cursor: pointer;
	transition: transform 0.2s ease-in-out;
}

.card:hover {
	transform: translateY(-5px);
	box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
}

.card img {
	width: 100%;
	height: 200px;
	object-fit: cover;
	margin: 0;
	border-radius: 10px 10px 0 0;
}

.card-body {
	padding: 20px;
	border-radius: 0 0 10px 10px;
	background-color: #f8f9fa;
}

.card-body h2 {
	font-weight: bold;
	font-size: 1.5rem;
	margin-top: 0;
	margin-bottom: 10px;
	color: #343a40;
}

.card-body p {
	margin: 0;
	color: #6c757d;
}
</style>
