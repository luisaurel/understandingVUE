<template>
<div class="counter">
<h3>Counter</h3>
<p>Count: {{ count }}</p>
<button @click="decrement">-</button>
<button @click="increment">+</button>
</div>
</template>

<script setup>
import { ref, watch } from 'vue'

const props = defineProps({ start: { type: Number, default: 0 } })
const emit = defineEmits(['update:count'])

const count = ref(props.start)

function increment() {
count.value++
emit('update:count', count.value)
}
function decrement() {
count.value--
emit('update:count', count.value)
}

watch(() => props.start, (v) => { count.value = v })
</script>

<style scoped>
.counter { border: 1px solid #ddd; padding: 0.5rem; display: inline-block }
</style>