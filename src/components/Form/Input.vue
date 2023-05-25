<template>
  <input type="text" :value="value" />
</template>

<script setup lang="ts">
defineOptions({
  name: 'FormInput'
})
defineProps({
  value: String
})
</script>

<style scoped></style>
