<template>
	<div>
		<button @click="plus">Click {{ state.count }}</button>
		<button @click="depPlus">Click {{ state.deep.count }}</button>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const state = reactive({
			count: 0,
			deep: {
				count: 0,
			},
		});
		const plus = () => {
			state.count++;
		};

		const depPlus = () => {
			state.deep.count++;
		};
		return {
			state,
			plus,
			depPlus,
		};
	},
};
</script>

<style lang="scss" scoped></style>
