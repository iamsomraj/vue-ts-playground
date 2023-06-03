<template>
  <Modal.Root>
    <Modal.Header>Hey there!</Modal.Header>
    <Modal.Body>
      <p>Are you sure you want to do this?</p>
    </Modal.Body>
    <Modal.Footer>
      <button type="button" @click="closeModal">Yes, I'm sure</button>
    </Modal.Footer>
  </Modal.Root>
</template>

<script setup lang="ts">
import * as Modal from '@/components/Modal/Modal'
defineOptions({
  name: 'ConfirmModal'
})
const emit = defineEmits<{
  (e: 'close'): void
}>()
const closeModal = () => {
  emit('close')
}
</script>

<style scoped>
dialog {
  border: solid 1px #ccc;
  border-radius: 8px;
  padding: 1rem;
  box-shadow: 0 0 100px rgba(0, 0, 0, 0.5);
}
button {
  margin: 0rem;
  padding: 0.5rem;
  border-radius: 4px;
  border: none;
  background-color: #ccc;
  cursor: pointer;
  font: 500 sans-serif;
}
dialog::backdrop {
  background-color: rgba(6, 4, 4, 0.5);
}
</style>
