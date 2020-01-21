<template>
	<div class="container">
		<form v-if="!submited">
			<div class="row">
				<div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
					<!-- Exercise 1 -->
					<!-- Create a Signup Form where you retrieve the following Information -->
					<!-- Full Name (First Name + Last Name) -->
					<!-- Mail -->
					<!-- Password -->
					<!-- Store Data? Yes/No -->

					<fullName v-model="fullName"></fullName>

					<div class="form-group">
						<label for="email">Email</label>

						<input
							type="email"
							id="email"
							class="form-control"
							v-model="userData.email"
							placeholder="i.e: email@domain.com"
						/>
					</div>

					<div class="form-group">
						<label for="password">password</label>

						<input
							type="password"
							id="password"
							class="form-control"
							v-model.lazy="userData.password"
							placeholder="*****"
						/>
					</div>

					<div class="form-group">
						<label for="yes">
							<input type="radio" id="yes" value="yes" v-model="isStored" /> yes
						</label>
						<label for="no">
							<input type="radio" id="no" value="no" v-model="isStored" /> no
						</label>
					</div>

					<!-- Exercise 2 -->
					<!-- Only display the Form if it has NOT been submitted -->
					<!-- Display the Data Summary ONCE the Form HAS been submitted -->

					<button @click.prevent="submit" class="btn btn-primary">Submit!</button>

					<!-- Exercise 3 -->
					<!-- Edit the Example from above and create a custom "Full Name" Control -->
					<!-- which still holds the First Name and Last Name Input Field -->
				</div>
			</div>
		</form>
		<hr />
		<div class="row" v-if="submited">
			<div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
				<div class="panel panel-default">
					<div class="panel-heading">
						<h4>Your Data</h4>
					</div>
					<div class="panel-body">
						<p>Full Name: {{fullName}}</p>
						<p>Mail: {{userData.email}}</p>
						<p>Password: {{userData.password}}</p>
						<p>Store in Database?: {{isStored}}</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import fullName from './FullName.vue'
	export default {
		data() {
			return {
				userData: {
					firstName: '',
					lastName: '',
					email: '',
					password: ''
				},
				isStored: false,
				submited: false,
				fullName: 'stephane goeuriot'
			}
		},
		methods: {
			submit() {
				this.submited = !this.submited
			}
		},
		components: {
			fullName
		}
	}
</script>

<style>
</style>
