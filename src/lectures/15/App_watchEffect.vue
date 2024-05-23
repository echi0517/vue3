<template>
	<div>
		<form action="" @submit.prevent>
			<input type="text" v-model.lazy="title" placeholder="title" />
			<textarea v-model.lazy="contents" placeholder="contents"></textarea>
			<!-- <input type="text" v-model="dd" /> -->
			<hr />
			<button @click="save(title, contents)">저장</button>
		</form>
	</div>
</template>

<script>
import { ref, watchEffect } from 'vue';

export default {
	setup() {
		const title = ref('');
		const contents = ref('');
		const dd = ref('');

		const save = (title, contents) => {
			console.log(`저장 ${title} , ${contents}`);
		};
		watchEffect(() => {
			save(title.value, contents.value);
		});
		return {
			title,
			contents,
			dd,
		};
	},
};
</script>

<style lang="scss" scoped></style>
