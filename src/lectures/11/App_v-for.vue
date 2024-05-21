<template>
	<div>
		<ul>
			<template v-for="(item, index) in evenItems" :key="item.id">
				<!-- <li v-if="index % 2 === 0"> -->
				<li>인덱스 : {{ item.id }} {{ item.message }}</li>
			</template>
			<ul>
				<li v-for="(value, key, index) in myObject" :key="key">
					{{ index }} - {{ key }} - {{ value }}
				</li>
			</ul>
		</ul>
	</div>
</template>

<script>
import { computed, reactive } from 'vue';

export default {
	setup() {
		const items = reactive([
			{ id: 1, message: 'Java' },
			{ id: 2, message: 'HTML' },
			{ id: 3, message: 'CSS' },
			{ id: 4, message: 'JavaScript' },
		]);

		const myObject = reactive({
			title: '제목',
			author: '홍길동',
			publishedAt: '2016.11.11',
		});

		const evenItems = computed(() => items.filter(item => item.id % 2 === 1));
		return { items, evenItems, myObject };
	},
};
</script>

<style lang="scss" scoped></style>
