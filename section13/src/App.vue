<template>
	<div class="container">
		<div class="row">
			<div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
				<h1>Filters & Mixins</h1>
				<p>{{ text | toUpperCase | toLow }}</p>
				<hr />
				<input type="text" v-model="filteredText" />
				<ul>
					<li :key="fruit" v-for="fruit in filteredFruits">{{ fruit }}</li>
				</ul>
			</div>
			<app-list></app-list>
		</div>
	</div>
</template>

<script>
	import List from './List.vue'
	export default {
		data() {
			return {
				text: 'hello world',
				fruits: ['apple', 'banana', 'mongo', 'melon'],
				filteredText: ''
			}
		},
		filters: {
			toUpperCase(value) {
				return value.toUpperCase()
			}
		},
		computed: {
			filteredFruits() {
				return this.fruits.filter(fruit => fruit.match(this.filteredText))
			}
		},
		components: {
			appList: List
		}
	}
</script>

<style>
</style>
