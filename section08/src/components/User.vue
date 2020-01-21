<template>
	<div class="component">
		<h1>The User Component</h1>
		<p>I'm {{ name }}, an awesome User!</p>
		<p>I'm {{ age }} years old</p>
		<button @click="changeName">Change my Name</button>
		<hr />
		<div class="row">
			<div class="col-xs-12 col-sm-6">
				<app-user-detail
					:myName="name"
					:userAge="age"
					@nameWasReset="name = $event"
					:resetFn="resetName"
				></app-user-detail>
			</div>
			<div class="col-xs-12 col-sm-6">
				<app-user-edit :userAge="age" @ageWasEdited="age = $event"></app-user-edit>
			</div>
		</div>
	</div>
</template>

<script>
	import UserDetail from './UserDetail.vue'
	import UserEdit from './UserEdit.vue'

	export default {
		data() {
			return {
				name: 'stephane',
				age: 45
			}
		},
		methods: {
			changeName() {
				this.name = 'lucien' // change name on click
			},
			resetName() {
				this.name = 'stephane'
			},
			resetAge() {
				this.age = 4
			}
		},
		components: {
			appUserDetail: UserDetail,
			appUserEdit: UserEdit
		}
	}
</script>

<style scoped>
	div {
		background-color: lightblue;
	}
</style>
