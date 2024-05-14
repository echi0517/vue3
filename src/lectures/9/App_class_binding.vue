<template>
	<div>
		<div class="text" :class="classObject">텍스트입니다</div>
		<button @click="toggle()">toggle</button>
		<button @click="hasError = !hasError">toggle</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);
		// const classObject = ref({
		// 	active: isActive,
		// 	'text-danger': hasError,
		// });

		const classObject = computed(() => {
			return {
				active: isActive.value,
				'text-danger': hasError.value,
			};
		});
		const toggle = () => (isActive.value = !isActive.value);

		return {
			isActive,
			toggle,
			hasError,
			classObject,
		};
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}
.text-danger {
	color: red;
}
</style>
