<template>
	<li class="list-group-item" @click="serverSelected">{{text}}{{server.id}}</li>
</template>
<script>
	import {serverBus} from '../../main'

	export default {
		data() {
			return {
				text: 'Server #'
			}
		},
		props: {
			server: Object,
		},
		methods: {
			serverSelected() {
				serverBus.$emit('serverSelected', this.server)
			}
		}
	}
</script>