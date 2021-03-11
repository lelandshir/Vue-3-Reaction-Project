<template>
	<div class="block" v-if="showBlock">
		click me
	</div>
</template>

<script>
export default {
	// 1. pass in the delay as a prop
	props: ["delay"],
	data() {
		return {
			//properties
			showBlock: false,
			timer: null, //setInterval
			reactionTime: 0,
			author: "Léland",
		};
	},
	// when the component mounts fire this code...
	mounted() {
		console.log(
			`Hello, ${this.author.toUpperCase()}! BLOCK component MOUNTED! 🟦`
		);
		setTimeout(() => {
			this.showBlock = true;
			this.startTimer();
			console.log(`delay = ${this.delay}`);
		}, this.delay);
	},
	//METHODS
	methods: {
		startTimer() {
			(this.timer = setInterval(() => {
				this.reaction += 10;
			})),
				10;
		},
		stopTimer() {},
	},
	// LIFE CYCLE HOOKS
	updated() {
		console.log("showBlock = true! BLOCK component UPDATED! 🟦");
	},
	// Comment component out to see this function fire
	unmounted() {
		console.log("BLOCK component UNMOUNTED! 🟦");
	},
};
</script>

<style lang="sass">
@import "../styles/global.sass"
.block
    width: 200px
    border-radius: 20px
    background: $primary
    color: #fff
    text-align: center
    padding: 60px 0
    margin: 40px auto
</style>
