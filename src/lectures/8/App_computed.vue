<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<!-- <p>{{ teacher.lectures.length ? '있음😀' : '없음😌' }}</p> -->
		<p>{{ hasLecture }}</p>
		<p>{{ exsitsLecture() }}</p>
		<button @click="count++">Click {{ count }}</button>
		<h2>{{ fullName }}</h2>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', 'JavaScript', 'Vue3'],
		});

		const hasLecture = computed(() => {
			console.log('computed');
			return teacher.lectures.length ? '있음😀' : '없음😌';
		});

		const exsitsLecture = () => {
			console.log('method');
			return teacher.lectures.length ? '있음😀' : '없음😌';
		};

		const count = ref(0);

		const firstName = ref('홍');
		const lastName = ref('길동');

		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});

		console.log('Console 출력: ', fullName.value);
		fullName.value = '짐 코딩';

		return { teacher, hasLecture, exsitsLecture, count, fullName };
	},
};
</script>

<style lang="scss" scoped></style>
