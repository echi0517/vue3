<template>
	<div>
		<p>{{ msg }}</p>
		<p v-text="msg"></p>
		<p v-html="htmlStr"></p>
		<p>{{ msg }}</p>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const msg = ref('안녕하세요');
		const htmlStr = ref('<b> 안녕!! </b>');
		return {
			msg,
			htmlStr,
		};
	},
};
</script>

<style lang="scss" scoped></style>
