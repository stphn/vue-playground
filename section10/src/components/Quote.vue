<template>
	<div>
		<div class="quote text-secondary">
			<slot></slot>
		</div>
	</div>
</template>
<script>
</script>
<style lang="css" scoped>
	.quote {
		border: 1px solid lightblue;
		font-family: Arizonia, sans-serif;
		font-size: 2em;
		padding: .5em;
		margin-bottom: 1em;
		content: '';
	}
</style>