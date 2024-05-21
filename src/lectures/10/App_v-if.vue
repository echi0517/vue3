<template>
	<div>
		<h2 v-if="visible">Hello Vue3!</h2>
		<h2 v-else>false 입니다.</h2>
		<button type="button" @click="visible = !visible">click</button>
		<hr />
		<h2 v-if="type === 'A'">A입니다.</h2>
		<h2 v-else-if="type === 'B'">B입니다.</h2>
		<h2 v-else-if="type === 'C'">C입니다.</h2>
		<h2 v-else>D입니다.</h2>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const visible = ref(false);
		const type = ref('A');
		return {
			visible,
			type,
		};
	},
};
</script>

<style lang="scss" scoped></style>
