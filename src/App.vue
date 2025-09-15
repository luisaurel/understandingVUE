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

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

.welcome-item {
  margin-top: 2rem;
  display: flex;
  position: relative;
}

.details {
  flex: 1;
  margin-left: 1rem;
}

i {
  display: flex;
  place-items: center;
  place-content: center;
  width: 32px;
  height: 32px;
  color: var(--color-text);
}

h3 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}

@media (min-width: 1024px) {
  .welcome-item {
    margin-top: 0;
    padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
  }

  i {
    top: calc(50% - 25px);
    left: -26px;
    position: absolute;
    border: 1px solid var(--color-border);
    background: var(--color-background);
    border-radius: 8px;
    width: 50px;
    height: 50px;
  }

  .welcome-item:before {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    bottom: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .welcome-item:after {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    top: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .welcome-item:first-of-type:before {
    display: none;
  }

  .welcome-item:last-of-type:after {
    display: none;
  }
}
</style>