<template>
  <Modal.Root :open="open">
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
defineProps<{
  open: Boolean
}>()
const emit = defineEmits<{
  (e: 'close'): void
}>()
const closeModal = () => {
  emit('close')
}
</script>

<style scoped></style>
