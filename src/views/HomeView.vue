<template>
  <div>
    <button @click="toggle">Toggle Confirm Modal</button>
    <ConfirmModal @close="toggle" v-if="showModal"></ConfirmModal>
  </div>
</template>

<script setup lang="ts">
import ConfirmModal from '@/components/ConfirmModal.vue'
import { ref } from 'vue'
const showModal = ref(false)
const toggle = () => {
  showModal.value = !showModal.value
}
</script>

<style scoped>
button {
  margin: 0rem;
  padding: 0.5rem;
  border-radius: 4px;
  border: none;
  background-color: #ccc;
  cursor: pointer;
  font-weight: 500;
}
</style>
