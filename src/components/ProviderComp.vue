<template>
<div>
<button @click="toggle">Toggle theme ({{ theme }})</button>
<ConsumerComp />
</div>
</template>

<script setup>
import { ref, provide } from 'vue'
import ConsumerComp from './ConsumerComp.vue'
const theme = ref('light')
function toggle() { theme.value = theme.value === 'light' ? 'dark' : 'light' }
provide('theme', theme)
</script>