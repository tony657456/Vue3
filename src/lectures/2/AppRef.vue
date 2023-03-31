<template>
	<div>{{ message }}</div>
	<button v-on:click="addMessage">add click</button>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		let message = ref('Hello Vue!');
		const addMessage = () => {
			message.value = message.value + '!';
		};
		return {
			message,
			addMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
