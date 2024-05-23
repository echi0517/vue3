<template>
	<div>
		<h2>hi222</h2>
	</div>
</template>

<script>
import { reactive, ref, watch } from 'vue';

export default {
	setup() {
		const x = ref(0);
		const y = ref(0);

		const obj = reactive({
			count: 0,
		});
		// watch(
		// 	() => x.value + y.value,
		// 	sum => {
		// 		console.log('sum', sum);
		// 	},
		// );

		watch([x, y], ([newX, newY]) => {
			console.log(newX, newY);
		});

		// watch(
		// 	() => obj.count,
		// 	(newValue, oldValue) => {
		// 		console.log(newValue);
		// 	},
		// );
		return { x, y, obj };
	},
};
</script>

<style lang="scss" scoped></style>
