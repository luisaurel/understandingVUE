<template>
<div class="parent-child-demo">
<h3>Parent → Child demo</h3>
<ChildItem :label="itemLabel" @remove="handleRemove" />
</div>
</template>

<script setup>
import { ref } from 'vue'
import ChildItem from './ChildItem.vue'
const itemLabel = ref('Ein Item aus dem Parent')
function handleRemove() { alert('Parent: Child asked to remove me!') }
</script>