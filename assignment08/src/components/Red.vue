<template>
	<div>
		<slot name="red">
			<h2>Red template</h2>
			<button @click="count --">DECREASE</button>
			<p>{{count}}</p>
		</slot>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				count: null
			}
		},
		activated() {
			return (this.count = 100)
		}
	}
</script>

<style scoped>
	div {
		border: 1px solid red;
		background-color: lightcoral;
		padding: 30px;
		margin: 20px auto;
		text-align: center;
	}
</style>