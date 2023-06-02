<template>
  <dialog open>
    <slot />
  </dialog>
</template>

<script setup lang="ts">
defineOptions({
  name: 'ModalRoot'
})
</script>

<style scoped></style>
