<template>
	<div class="section">
		<form>
			<div class="form-group">
				<label for="exampleFormControlTextarea1">Quote</label>
				<textarea
					style="white-space: pre-line;"
					class="form-control"
					id="exampleFormControlTextarea1"
					rows="3"
					v-model="quote.text"
				></textarea>
			</div>
			<button @click.prevent="createNew" type="button" class="btn btn-primary">ADD QUOTE</button>
		</form>
		<hr />
	</div>
</template>

<script>
	export default {
		data() {
			return {
				quote: {
					text: null,
					id: 0
				}
			}
		},
		methods: {
			createNew() {
				if (this.quote.text != null) {
					this.formatText(this.quote.text)
					this.quote.id = this.quote.id + 1
					this.$emit('quoteAdded', this.quote)
					this.quote.text = null
				}
			},
			formatText(strg) {
				let s
				s = strg.replace(/[^\w\s]/g, '') // Remove all non-word characters
				s = s.replace(/\s+/g, ' ') // Replace remaining double spaces for single space
				return s.split(' ').join('_') // then add underscores
			}
		}
	}
</script>