<template>
	<p>
		Reaction Time (in millseconds): <span id="score">{{ score }}</span>
	</p>
	<b id="rank">{{ rank }}</b>
</template>

<script>
export default {
	props: ["score"],
	data() {
		return {
			rank: null,
		};
	},
	mounted() {
		if (this.score < 250) {
			this.rank = "Speedy Fingers... 👋🏼";
		} else if (this.score < 400) {
			this.rank = "Quick reflexes... 🦈";
		} else {
			this.rank = "Turtle's are cool too... 🐢";
		}
	},
};
</script>

<style lang="sass">
@import "../styles/global.sass"
p
  font-weight: 600

#score
  color: $secondary

#rank
    font-size: 1.5rem
    color: $primary
</style>
