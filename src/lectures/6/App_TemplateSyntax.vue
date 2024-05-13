<template>
	<div>
		<h2>보간법</h2>
		<p>{{ message }}</p>
		<p v-once>{{ message }}</p>
		<button @click="message = message + '!'">click</button>
		<hr />
		<h2>v-html</h2>
		<p>{{ rawHtml }}</p>
		<p v-html="rawHtml"></p>
		<hr />
		<div :title="dyTitle">마우스를 올려보세요</div>
		<input v-bind="attrs" />

		<h2>JavaScript</h2>
		{{ message.split('').reverse().join('') }}<br />
		{{ treu ? '예' : '아니요' }}
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const message = ref('안녕하세요');
		const rawHtml = ref('<b>안녕하세요</b>');
		const dyTitle = ref('우하ㅣ하하ㅏ');
		const attrs = ref({
			type: 'text',
			value: '12345678',
			disalbed: false,
		});

		return {
			message,
			rawHtml,
			dyTitle,
			attrs,
		};
	},
};
</script>

<style lang="scss" scoped></style>
