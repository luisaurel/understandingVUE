<template>
<div>
<h3>Dynamic component demo</h3>
<button @click="current = 'CompA'">A</button>
<button @click="current = 'CompB'">B</button>
<component :is="currentComponent" />
</div>
</template>

<script setup>
import { ref, computed } from 'vue'
const current = ref('CompA')
const CompA = { template: '<div>Component A</div>' }
const CompB = { template: '<div>Component B</div>' }
const currentComponent = computed(() => current.value === 'CompA' ? CompA : CompB)
</script>