<template>
	<div>
		<h2>보간법</h2>
		<p>{{ message }}</p>
		<p v-once>{{ message }}</p>
		<button v-on:click="message = message + '!'">click</button>
		<hr />

		<h2>HTML</h2>
		<p>{{ html }}</p>
		<p v-html="html"></p>
		<hr />

		<h2>속성 바인딩</h2>
		<div v-bind:title="dynamicTitle">마우스를 올려보세요</div>
		<input type="text" value="홍길동" v-bind:disabled="isInputDisalbed" />
		<hr />

		<h2>다중 속성 바인딩</h2>
		<input :="attrs" />
		<hr />

		<h2>JavaScript</h2>
		{{ message.split('').reverse().join('') }}
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const message = ref('안녕하세요!');
		const html = ref('<strong>안녕하십니까</strong>');
		const dynamicTitle = ref('안녕하세요');
		const isInputDisalbed = ref(false);
		const attrs = ref({
			text: 'password',
			value: 123456789,
			disabled: false,
		});
		return {
			message,
			html,
			dynamicTitle,
			isInputDisalbed,
			attrs,
		};
	},
};
</script>

<style lang="scss" scoped></style>
