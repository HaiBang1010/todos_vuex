<template>
	<form @submit="onSubmit">
		<input type="text" v-model="title" />
		<button class="submit" value="Add">ADD</button>
	</form>
</template>

<script>
import { mapActions } from 'vuex'
import { v4 as uuidv4 } from 'uuid'

export default {
	name: 'TodoForm',
	data() {
		return {
			title: ''
		}
	},
	methods: {
		...mapActions(['addTodo']), // addTodo() === this.$store.dispatch('addTodo')
		onSubmit(event) {
			event.preventDefault()
			// console.log(this.title)
			this.addTodo({
				id: uuidv4(),
				title: this.title,
				completed: false
			})
			this.title = ''
		}
	}
}
</script>

<style>
form {
	padding: 0px;
	text-align: center;
}

input[type='text'] {
	width: 50%;
	box-sizing: border-box;
	padding: 10px;
	margin: 6px 10px;
	border: 0;
	border-radius: 6px;
}

.submit {
	margin: 10px auto;
	cursor: pointer;
	padding: 10px;
	border: 0;	
	border-radius: 6px;
}
</style>
