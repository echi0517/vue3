<template>
	<div>
		<p>{{ count }}</p>

		<p>{{ message }}</p>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const count = ref(0);
		const message = ref('Hellpo Vue3');

		return {
			count,
			message,
		};
	},
};
</script>

<style lang="scss" scoped></style>
