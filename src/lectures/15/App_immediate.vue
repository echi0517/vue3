<template>
	<div>
		<p>{{ msg }}</p>
		<p>{{ reverseMsg }}</p>
	</div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const msg = ref('Hello Vue3');

		const reverseMsg = ref('');

		watch(
			msg,
			newValue => {
				reverseMsg.value = newValue.split('').reverse().join('');
			},
			{ immediate: true },
		);
		return { msg, reverseMsg };
	},
};
</script>

<style lang="scss" scoped></style>
