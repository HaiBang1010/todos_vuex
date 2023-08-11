<template>
	<div id="app">
		<Navbar />
		<Todos />
	</div>
</template>

<script>
import Todos from './components/Todos'
import Navbar from './components/Navbar'

export default {
	name: 'App',
	components: { Todos, Navbar }
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	background: rgb(219, 219, 219);
	margin: 20px auto;
	width: 100%;
	max-width: 800px;
}
body{
	width: auto;
	height: 100%;
	background: url('./assets/background.jpg') no-repeat fixed 	 ;
	background-size: 100%;
}
</style>
