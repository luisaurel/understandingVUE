<template>
<div class="child-item">
<span>{{ label }}</span>
<button @click="$emit('remove')">Remove</button>
</div>
</template>

<script setup>
const props = defineProps({ label: { type: String, default: '' } })
</script>