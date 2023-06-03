<template>
  <dialog ref="dialog">
    <slot />
  </dialog>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
defineOptions({
  name: 'ModalRoot'
})
const dialog = ref<HTMLDialogElement | null>(null)
onMounted(() => {
  dialog.value?.showModal()
})
onUnmounted(() => {
  dialog.value?.close()
})
</script>
