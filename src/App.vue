<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus odit
			corporis maxime optio recusandae, architecto culpa ullam nisi iure impedit
			nulla blanditiis eveniet quia, repudiandae neque nam fugit deserunt quas!
		</div>
		<button>-</button>
		<button>+</button>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		// const styleObject = reactive({
		// 	color: 'red',
		// 	fontSize: '13px',
		// });
		const fontSize = ref(13);
		const styleObject = computed(() => {
			return {
				color: 'blue',
				fontSize: fontSize.value + 'px',
			};
		});
		return {
			styleObject,
		};
	},
};
</script>

<style lang="scss" scoped></style>
