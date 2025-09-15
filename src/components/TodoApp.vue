<template>
<div class="todo-app">
<h3>Todo App</h3>
<input v-model="newTodo" @keyup.enter="addTodo" placeholder="Neues Todo" />
<button @click="addTodo">Add</button>
<ul>
<li v-for="(item, i) in todos" :key="i">
{{ item }}
<button @click="remove(i)">x</button>
</li>
</ul>
</div>
</template>

<script setup>
import { ref } from 'vue'
const newTodo = ref('')
const todos = ref(['Erstes Todo', 'Zweites Todo'])
function addTodo() {
if (newTodo.value.trim() === '') return
todos.value.push(newTodo.value.trim())
newTodo.value = ''
}
function remove(i) { todos.value.splice(i,1) }
</script>

<style scoped>
.todo-app { margin-top: 1rem }
</style>