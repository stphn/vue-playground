<template>
	<div>
		<slot name="green">
			<h1>default green slot content</h1>
			<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae, praesentium illo! Aspernatur!</p>
		</slot>
	</div>
</template>

<script>
</script>

<style scoped>
	div {
		border: 1px solid green;
		background-color: lightgreen;
		padding: 30px;
		margin: 20px auto;
		text-align: center;
	}
</style>