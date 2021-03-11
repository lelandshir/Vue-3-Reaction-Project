<template>
	<p>
		Reaction Time (in millseconds): <span id="score">{{ score }}</span>
	</p>
</template>

<script>
export default {
	props: ["score"],
};
</script>

<style lang="sass">
@import "../styles/global.sass"
p
  font-weight: 600

#score
  color: $secondary
</style>
