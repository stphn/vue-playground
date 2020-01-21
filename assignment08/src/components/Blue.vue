<template>
	<div>
		<slot name="blue">
			<h1>default blue slot content</h1>
			<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae, praesentium illo! Aspernatur!</p>
		</slot>
	</div>
</template>

<script>
	export default {
		// data() {
		// 	return {
		// 		name: 'stephane',
		// 		age: 45
		// 	}
		// },
		props: {
			myName: String
		}
	}
</script>

<style scoped>
	div {
		border: 1px solid blue;
		background-color: lightblue;
		padding: 30px;
		margin: 20px auto;
		text-align: center;
	}
</style>