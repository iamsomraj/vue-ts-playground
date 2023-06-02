<template>
  <div>
    <button @click="toggle">Toggle Confirm Modal</button>
    <ConfirmModal @close="toggle" :open="showModal"></ConfirmModal>
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
