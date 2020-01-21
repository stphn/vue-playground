<template>
	<div class="container">
		<div class="row">
			<div class="col-xs-12">
				<button @click="selectedComponent = 'awesomeQuote'">Quote Component</button>
				<button @click="selectedComponent = 'awesomeAuthor'">Author Component</button>
				<button @click="selectedComponent = 'awesomeNew'">New Component</button>
				<hr />
				{{selectedComponent}}
				<hr />
				<keep-alive>
					<component :is="selectedComponent"></component>
				</keep-alive>
				<!-- <awesomeQuote>
					<h2 slot="title">{{title}}</h2>
					<span slot="subtitle">dasdasdasds</span>
					<p>A wondefull quote</p>
				</awesomeQuote>
				<awesomeAuthor></awesomeAuthor>
				<awesomeNew></awesomeNew>-->
			</div>
		</div>
	</div>
</template>

<script>
	import Quote from './components/Quote.vue'
	import Author from './components/Author.vue'
	import New from './components/New.vue'
	export default {
		data() {
			return {
				selectedComponent: 'awesomeQuote',
				title: 'hello world'
			}
		},
		components: {
			awesomeQuote: Quote,
			awesomeAuthor: Author,
			awesomeNew: New
		}
	}
</script>

<style>
	a {
		font-size: 0;
	}

	p {
		height: .9em;
	}
</style>
