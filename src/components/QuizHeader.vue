<script setup>
import { defineProps } from "vue";
const { questionPage } = defineProps(["questionPage"]);
</script>

<template>
	<header>
		<h4>{{ questionPage }}</h4>
		<div class="bar">
			<div class="bar-progress"></div>
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
	width: 50%;
	background-color: #f8ad54;
}
</style>
