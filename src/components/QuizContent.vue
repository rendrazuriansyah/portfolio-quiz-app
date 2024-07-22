<template>
	<section id="question-container">
		<h1 class="question-title">What is the capital of France?</h1>
	</section>
	<section id="options-container">
		<div class="option">
			<p class="option-label">A.</p>
			<div class="option-value">Berlin</div>
		</div>
		<div class="option">
			<p class="option-label">B.</p>
			<div class="option-value">Madrid</div>
		</div>
		<div class="option">
			<p class="option-label">C.</p>
			<div class="option-value">Paris</div>
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
	width: 50px;
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
