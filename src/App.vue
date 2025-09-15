<template>
<div id="app">
<h1>Vue 3 — Komponenten Demo</h1>

<!-- Counter: zeigt Props, v-model:count, emits -->
<Counter :start="5" v-model:count="sharedCount" />
<p>Shared count in App: {{ sharedCount }}</p>

<!-- Todo-Liste: lokale State / v-model on inputs -->
<TodoApp />

<!-- Parent/Child: props und emits -->
<ParentChildDemo />

<!-- Slots: default und named slots -->
<SlotDemo>
<template #header>
<h2>Header via named slot</h2>
</template>

<template #footer>
<small>Footer via named slot</small>
</template>
</SlotDemo>

<!-- Dynamische Komponenten -->
<DynamicComponentDemo />

<!-- provide / inject -->
<ProvideInjectDemo />
</div>
</template>

<script setup>
import { ref } from 'vue'
import Counter from './components/Counter.vue'
import TodoApp from './components/TodoApp.vue'
import ParentChildDemo from './components/ParentChildDemo.vue'
import SlotDemo from './components/SlotDemo.vue'
import DynamicComponentDemo from './components/DynamicComponentDemo.vue'
import ProvideInjectDemo from './components/ProvideInjectDemo.vue'

const sharedCount = ref(0)
</script>

<style>
#app { font-family: Arial, sans-serif; padding: 1rem }
button { margin-left: 0.5rem }
</style>