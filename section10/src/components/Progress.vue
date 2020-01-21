<template>
	<div class="section">
		<h1>Quotes Added</h1>
		<div class="progress">
			<div
				class="progress-bar"
				role="progressbar"
				:style="{width: (quotesCount / maxQuotes)  * 100  + '%'}"
				aria-valuemin="0"
				aria-valuemax="100"
			>{{quotesCount}}/{{maxQuotes}}</div>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			quotesCount: Number,
			maxQuotes: Number
		}
	}
</script>