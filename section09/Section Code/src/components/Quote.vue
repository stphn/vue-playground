<template>
	<div class="quote">
		<div>
			<slot name="title"></slot>
			<span>
				<slot name="subtitle">my subtitle</slot>
			</span>
		</div>
		<div>
			<slot></slot>
		</div>
	</div>
</template>

<script>
	export default {}
</script>

<style scoped>
	.quote {
		border: 4px solid darksalmon;
		background-color: antiquewhite;
		padding: 2em;
		font-size: 2em;
		text-align: center;
		margin: 1em 0;
		box-shadow: 0 5px 12px rgba(0, 0, 0, .25);
	}

	h2 {
		color: brown;
	}
</style>