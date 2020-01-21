<template>
	<div>
		<div>
			<app-quote
				@click.native="deleteQuote(index)"
				:key="quote.id"
				v-for="(quote,index) in quotes"
			>{{ quote }}</app-quote>
		</div>
	</div>
</template>

<script>
	import Quote from './Quote.vue'

	export default {
		data() {
			return {
				arrayOfQuotes: ['just something to start with'],
				maxQuotes: 10
			}
		},
		props: ['quotes'],
		components: {
			appQuote: Quote
		},
		methods: {
			deleteQuote(index) {
				this.$emit('quoteDeleted', index)
			}
		}
	}
</script>