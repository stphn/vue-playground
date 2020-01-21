<template>
	<!-- :value="userData.email"
	@input="userData.email = $event.target.value"-->
	<div>
		<label>Fullname</label>
		<div class="form-row">
			<div class="col">
				<input
					:value="firstName"
					@change="change(firstName)"
					type="text"
					class="form-control"
					placeholder="First name"
				/>
			</div>
			<div class="col">
				<input
					:value="lastName"
					@change="change(lastName)"
					type="text"
					class="form-control"
					placeholder="Last name"
				/>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		props: ['value'],
		methods: {
			change(value) {
				this.$emit('change', value)
			}
		},
		computed: {
			firstName() {
				return this.value.split(' ')[0]
			},
			lastName() {
				return this.value.split(' ')[1]
			}
		}
	}
</script>
<style scoped>
</style>