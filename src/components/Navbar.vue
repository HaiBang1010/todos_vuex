<template>
	<div class="navbar">
		<h1>My Vuex App Todos</h1>
		<ul>
			<li>Home</li>
			<li><ProgressBar/></li>
			<li v-if="isAuthenticated">
				Total todos: {{ todos.length }}
				<button @click="TOGGLE_AUTH">Logout</button>
			</li>
			<button v-else @click="TOGGLE_AUTH">Login</button>
		</ul>
	</div>
</template>

<script>
import { mapMutations, mapGetters } from 'vuex'
import ProgressBar from './ProgressBar'
export default {
	name: 'Navbar',
	components: {  ProgressBar },
	computed: mapGetters(['todos', 'isAuthenticated']),
	methods: mapMutations(['TOGGLE_AUTH'])
}
</script>

<style>
.navbar {
	padding: 4px;
	text-align: center;
	background: rgb(240, 240, 240);
	color: black;
}

.navbar ul {
	display: flex;
	justify-content: space-around;
	align-items: center;
	list-style: none;
	padding: 0;
}
</style>
