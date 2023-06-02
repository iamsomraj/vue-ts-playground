<template>
  <dialog ref="dialog">
    <slot />
  </dialog>
</template>

<script setup lang="ts">
import { computed, ref, watch } from 'vue'

defineOptions({
  name: 'ModalRoot'
})
const props = defineProps<{
  open: Boolean
}>()
const showModal = computed(() => props.open)
const dialog = ref<HTMLDialogElement | null>(null)
watch(
  () => showModal.value,
  (open) => {
    if (dialog.value) {
      if (open) {
        dialog.value.showModal()
      } else {
        dialog.value.close()
      }
    }
  }
)
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
