<template>
	<div class="container">
		<div class="row">
			<div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
				<h1>Directives Exercise</h1>
				<!-- Exercise -->
				<!-- Build a Custom Directive which works like v-on (Listen for Events) -->
				<div class="button" v-myOn:click.delayed="{delay: 1000}">click me and check the console!!</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		directives: {
			myOn: {
				bind(el, binding, vnode) {
					let delay = 0

					if (binding.modifiers['delayed']) {
						delay = binding.value.delay
					}

					if (binding.arg === 'click') {
						el.addEventListener('click', () => {
							console.log(`waiting: ${delay} ms`)

							setTimeout(() => {
								console.log(`done after: ${delay} ms`)
							}, delay)
						})
					}
				}
			}
		}
	}
</script>

<style>
	.button {
		padding: 1em;
		border: 4px solid rgb(252, 119, 3);
		background-color: rgb(1, 13, 15);
		color: rgb(238, 143, 99);
		text-align: center;
		text-transform: uppercase;
		font-weight: bold;
	}
</style>
