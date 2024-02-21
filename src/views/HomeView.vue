<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
import { ref } from 'vue'
const awesome = ref(false)
const message = ref('')
const items = ref(['a','b','c'])
function handleClick() {
  items.value[0] = message.value
}
</script>

<template>
  <main>
    <TheWelcome />
    <button @click="awesome=!awesome">Toggle title</button>
    <h1 v-if="awesome">Vue is awesome!</h1>
    <p>Message is: {{ message }}</p>
    <input v-model="message" placeholder="edit me" />
    <button :class="{ button: true, active: !!message }" @click="handleClick">Change first item</button>
    <ul>
      <li v-for="item in items">
        {{ item }}
      </li>
    </ul>
  </main>
</template>

<style scoped>
button {
  background: grey;
}
.active {
  background: white;
}
</style>