<template>
	<h1>Vue App 1.0: Reaction Timer</h1>
	<button @click="startGame" :disabled="isPlaying">play</button>
	<Block v-if="isPlaying" :delay="delay" />
</template>

<script>
import Block from "./components/Block.vue";

export default {
	name: "App",
	components: { Block },
	data() {
		return {
			isPlaying: false,
			delay: null,
		};
	},
	methods: {
		startGame() {
			this.delay = 2000 + Math.random() * 5000;
			this.isPlaying = true;
			// console.log(this.delay);
		},
	},
};
</script>

<style lang="sass">
@import "../src/styles/global.sass"
</style>
