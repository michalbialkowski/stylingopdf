<template>
	<div></div>
</template>

<script>
	import domtoimage from 'dom-to-image';
	
	export default {
		name: 'App',
		components: {
		},
		setup() {
			var node = document.getElementById('print');
			
			domtoimage.toPng(node)
			.then(function (dataUrl) {
				var img = new Image();
				img.src = dataUrl;
				document.body.appendChild(img);
			})
			.catch(function (error) {
				console.error('oops, something went wrong!', error);
			});
		}
	}
</script>

<style>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
