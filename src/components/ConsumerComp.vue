<template>
<div>Injected theme: {{ theme }}</div>
</template>

<script setup>
import { inject, ref } from 'vue'
const theme = inject('theme', ref('unknown'))
</script>