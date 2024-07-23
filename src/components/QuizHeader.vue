<script setup>
import { defineProps } from "vue";
const { questionPage, barPercentage } = defineProps([
	"questionPage",
	"barPercentage",
]);
</script>

<template>
	<header>
		<h4>{{ questionPage }}</h4>
		<div class="bar">
			<div class="bar-progress" :style="{ width: barPercentage }"></div>
		</div>
	</header>
</template>

<style scoped>
header {
	margin-top: 30px;
}

header h4 {
	font-size: 32px;
	color: #343a40;
	text-align: center;
}

.bar {
	width: 100%;
	height: 60px;
	border: 3px solid #f8ad54;
	margin: 30px 0;
	border-radius: 10px;
}

.bar-progress {
	height: 100%;
	width: 0%;
	background-color: #f8ad54;
}
</style>
