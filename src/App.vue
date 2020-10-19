<template>
	<section id="app">
		<h1>toDo</h1>
		<form v-on:submit.prevent="saveNewItem">
			<input type="text" v-model="newItem" placeholder="add toDo here" />
			<button v-on:click="addNewItem">Add toDo Item</button>
		</form>
		<ul>
			<li v-for="todo in todos">
				<span>{{ todo }}</span>
			</li>
		</ul>
	</section>
</template>

<script>
export default {
	data() {
		return {
			todos: ['Buy shopping', 'Clean bathroom', "Car's MOT"],
			newItem: ''
		};
	},
	methods: {
		addNewItem: function() {
			this.todos.push(this.newItem);
			this.newItem = '';
		}
	}
};
</script>

<style scoped></style>
