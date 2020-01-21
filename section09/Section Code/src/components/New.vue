<template>
	<div>
		<h1>New Component</h1>
		<button @click="count ++">increase</button>
		<h2>{{count}}</h2>
	</div>
</template>
<script>
	export default {
		data() {
			return {
				count: 0
			}
		},
		destroyed() {
			console.log(`TCL: destroy -> destroy`)
		},
		deactivated() {
			console.log('daeactivated')
		},
		activated() {
			console.log('activated')
		}
	}
</script>