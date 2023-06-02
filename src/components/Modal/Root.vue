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

<style scoped>
dialog {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

dialog::backdrop {
  background-color: rgba(6, 4, 4, 0.5);
}
</style>
