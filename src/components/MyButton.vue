<template>
  <button class="my-button" @click="$emit('click')">
    {{ label }}
  </button>
</template>

<script setup>
const props = defineProps({
  label: { type: String, default: "Klick mich" }
})
</script>

<style scoped>
.my-button {
  background: #42b983;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
}
</style>
