<template>
	<div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
		<h1>Filters & Mixins</h1>
		<hr />
		<input type="text" v-model="filteredText" />
		<ul>
			<li :key="fruit" v-for="fruit in filteredFruits">{{ fruit }}</li>
		</ul>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				fruits: ['apple', 'banana', 'mongo', 'melon'],
				filteredText: ''
			}
		},
		computed: {
			filteredFruits() {
				return this.fruits.filter(fruit => fruit.match(this.filteredText))
			}
		}
	}
</script>

<style>
</style>
