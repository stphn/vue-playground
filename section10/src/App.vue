<template>
	<div class="container">
		<app-Progress :quotesCount="arrayOfQuotes.length" :maxQuotes="maxQuotes"></app-Progress>
		<app-Form @quoteAdded="newQuote"></app-Form>
		<app-Quotes @quoteDeleted="deleteQuote" :quotes="arrayOfQuotes"></app-Quotes>
		<div class="p-3 mb-2 bg-info text-white">.bg-info</div>
	</div>
</template>

<script>
	import Progress from './components/Progress.vue'
	import Form from './components/Form.vue'
	import Quotes from './components/Quotes.vue'
	export default {
		data() {
			return {
				arrayOfQuotes: ['just something to start with'],
				maxQuotes: 10
			}
		},
		components: {
			appProgress: Progress,
			appForm: Form,
			appQuotes: Quotes
		},
		methods: {
			newQuote(quote) {
				this.arrayOfQuotes.push(quote.text)
			},
			deleteQuote(index) {
				this.arrayOfQuotes.splice(index, 1)
			}
		}
	}
</script>

<style>
	.section {
		margin-bottom: 2em;
	}
</style>
