<template>
  <div id="app">
    <h1>Vue 3 — Komponenten Demo</h1>

    <Counter :start="5" v-model:count="sharedCount" />
    <p>Shared count in App: {{ sharedCount }}</p>

    <TodoApp />

    <ParentChildDemo />

    <SlotDemo>
      <template #header>
        <h2>Header via named slot</h2>
      </template>
      <template #footer>
        <small>Footer via named slot</small>
      </template>
    </SlotDemo>

    <DynamicComponentDemo />

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
/* WICHTIG: "scoped" wurde entfernt, damit diese Stile global gelten
  und auch die importierten Komponenten gestylt werden.
*/

/* 1. Grundlegende Styles & Farb-Variablen */
:root {
  --bg-color: #1a1a1a;
  --text-color: #e0e0e0;
  --primary-color: #42b883; /* Vue Green */
  --border-color: #444;
  --card-bg: #242424;
}

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  background-color: var(--bg-color);
  color: var(--text-color);
  line-height: 1.6;
}

/* 2. Layout des Hauptcontainers */
#app {
  max-width: 900px;
  margin: 40px auto;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 25px; /* Abstand zwischen den Demo-Komponenten */
}

/* 3. Typografie */
h1 {
  font-size: 2.5em;
  text-align: center;
  color: var(--primary-color);
  font-weight: 600;
  margin-bottom: 0;
}

h2 {
  color: var(--primary-color);
  border-bottom: 1px solid var(--border-color);
  padding-bottom: 8px;
  margin-top: 0;
}

/* 4. Styling für die einzelnen Demo-Komponenten */
/* Der Selektor "> *" wählt alle direkten Kind-Elemente von #app aus. */
#app > div, #app > section {
  background-color: var(--card-bg);
  padding: 25px;
  border-radius: 12px;
  border: 1px solid var(--border-color);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  transition: transform 0.2s ease-in-out;
}

#app > div:hover, #app > section:hover {
  transform: translateY(-4px);
}

/* Spezifische Ausnahme für den "shared count" Text, damit er keine Box hat */
#app > p {
  text-align: center;
  font-size: 1.2em;
  font-weight: bold;
  color: #aaa;
  margin-top: -15px;
}

/* 5. Styling für Formularelemente (wichtig für Counter, TodoApp etc.) */
button {
  background-color: var(--primary-color);
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1em;
  font-weight: bold;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s;
  margin: 5px 0;
}

button:hover {
  background-color: #36a473;
}

input[type="text"] {
  padding: 10px;
  border-radius: 8px;
  border: 1px solid var(--border-color);
  background-color: #333;
  color: var(--text-color);
  font-size: 1em;
  width: calc(100% - 22px); /* Korrektur für padding und border */
  margin-bottom: 10px;
}

input[type="text"]:focus {
  outline: none;
  border-color: var(--primary-color);
}
</style>