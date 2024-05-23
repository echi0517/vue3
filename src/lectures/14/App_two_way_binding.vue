<template>
	<div>
		<h2>input value</h2>
		<input type="text" v-model.trim="inputValue" />
		<!-- :value="inputValue" @input="event => (inputValue = event.target.value)" -->
		<div>{{ inputValue }}</div>
		<div>{{ typeof inputValue }}</div>
		<h2>text area</h2>
		<textarea
			:value="textArea"
			@input="event => (textArea = event.target.value)"
		></textarea>
		<div>{{ textArea }}</div>

		<h2>check box</h2>
		<label for="checkbox2"> {{ checkBoxValue }}</label>
		<input
			type="checkbox"
			id="checkbox"
			v-model="checkBoxValue"
			true-value="yes"
			false-value="no"
		/>
		<!-- :checked="checkBoxValue"
			@change="event => (checkBoxValue = event.target.checked)" -->
		<div>
			<label for="">
				<input type="checkbox" value="HTML" v-model="checkboxValues" />
				HTML
			</label>
			<label for="">
				<input type="checkbox" value="CSS" v-model="checkboxValues" />
				CSS
			</label>
			<label for="">
				<input type="checkbox" value="JAVASCRIPT" v-model="checkboxValues" />
				javascript
			</label>
			{{ checkboxValues }}
		</div>
		<h2>radio value</h2>
		<label>
			<input
				type="radio"
				name="type"
				value="O"
				:checked="radioValue === 'O'"
				@change="event => (radioValue = event.target.value)"
			/>
			O형
		</label>
		<label>
			<input
				type="radio"
				name="type"
				value="B"
				:checked="radioValue === 'B'"
				@change="event => (radioValue = event.target.value)"
			/>
			B형
		</label>
		<label>
			<input
				type="radio"
				name="type"
				value="AB"
				:checked="radioValue === 'AB'"
				@change="event => (radioValue = event.target.value)"
			/>
			AB형
		</label>
		<label>
			<input type="radio" name="type" value="A" v-model="radioValue" />
			<!-- :checked="radioValue === 'A'"
				@change="event => (radioValue = event.target.value) -->
			A형
		</label>
		<div>
			{{ radioValue }}
		</div>
		<h2>select value</h2>
		<select v-model="selectValue">
			<option value="html">HTML 수업</option>
			<option value="css">CSS 수업</option>
			<option value="javascript">JavaScript 수업</option>
		</select>
		<div>{{ selectValue }}</div>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const inputValue = ref('');
		const textArea = ref('');
		const checkBoxValue = ref(true);
		const radioValue = ref('O');
		const selectValue = ref('html');
		const checkboxValues = ref([]);

		return {
			inputValue,
			textArea,
			checkBoxValue,
			radioValue,
			selectValue,
			checkboxValues,
		};
	},
};
</script>

<style lang="scss" scoped></style>
