<template>
	<h1>Vue 3 App 1.1: Reaction Timer</h1>
	<button @click="startGame" :disabled="isPlaying">play</button>
	<!-- grab the emit by adding it as a prop by @name and passing the function that will use the data that was passed  -->
	<Block v-if="isPlaying" :delay="delay" @end="endGame" />
	<Results v-if="showResults" :score="score" />
</template>

<script>
import Block from "./components/Block";
import Results from "./components/Results";

export default {
	name: "App",
	components: { Block, Results },
	data() {
		return {
			isPlaying: false,
			delay: null,
			score: null,
			showResults: false,
		};
	},
	methods: {
		startGame() {
			this.showResults = false;
			this.delay = 2000 + Math.random() * 5000;
			this.isPlaying = true;
			// console.log(this.delay);
		},
		// pass the data into the parameter of the specified method - could be `asdf`
		endGame(reactionTime) {
			this.score = reactionTime;
			this.isPlaying = false;
			this.showResults = true;
		},
	},
};
</script>

<style lang="sass">
@import "../src/styles/global.sass"
button
  background: $primary
  color: #fff
  border: none
  padding: 8px 16px
  font-size: 1rem
  letter-spacing: 1.5px
  cursor:pointer
  margin: .5rem

button[disabled]
  opacity: 0.2
  cursor: not-allowed
</style>
