<template>
	<div class="col-xs-12 col-sm-6">
		<ul class="list-group" :key="server.id" v-for="server in servers">
			<my-Server :server="server"></my-Server>
		</ul>
	</div>
</template>

<script>
import Server from './Server.vue'

export default {
	data() {
		return {
			servers : [
				{ id: 1,status: 'normal'},
				{ id: 2,status: 'critical'},
				{ id: 3,status: 'fantastic'},
				{ id: 4,status: 'abnormal'},
				{ id: 5,status: 'super'}
			]
		}
	},
	components : {
		'my-Server' : Server
	}
}
</script>

<style>
</style>
