<template>
  <button @click="ocClick">
    <slot />
  </button>
</template>

<script setup lang="ts">
const emit = defineEmits(['click'])
const ocClick = () => emit('click')
</script>

<style scoped lang="scss">
@use '@/assets/scss/colors' as *;

button {
  font-size: 1.8rem;
  border: 0;
  color: inherit;
  background: linear-gradient(to left, #13adc7, #6978d1, #945dd6);
  width: max-content;
  border-radius: 2rem;
  padding: 1rem 2rem;
}
</style>
