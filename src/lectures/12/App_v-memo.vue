<template>
	<div>
		<div v-memo="[views]">
			<p>subscrubers : {{ subscrubers }}</p>
			<p>views : {{ views }}</p>
			<p>likes : {{ likes }}</p>
		</div>
		<button @click="subscrubers++">Sub++</button>
		<button @click="views++">Views++</button>
		<button @click="likes++">likes++</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const subscrubers = ref(4000);
		const views = ref(400);
		const likes = ref(2);
		return {
			subscrubers,
			views,
			likes,
		};
	},
};
</script>

<style lang="scss" scoped></style>
