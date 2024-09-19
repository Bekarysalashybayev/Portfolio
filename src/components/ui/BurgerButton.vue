<template>
  <div class="burger-button" @click="model =!model" :class="[model && 'open']" aria-label="burger button">
    <span class="line"></span>
    <span class="line"></span>
    <span class="line"></span>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  modelValue: boolean
}>()

const emit = defineEmits(['update:modelValue', 'click']);

const model = computed({
  get: () => props.modelValue,
  set: (value) => emit('update:modelValue', value)
})
</script>

<style scoped lang="scss">
.burger-button {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 32px;
  height: 24px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;

  .line {
    width: 100%;
    height: 4px;
    background-color: #ffffff;
    border-radius: 2px;
    transition: all 0.3s ease;
  }

  &.open .line:nth-child(1) {
    transform: translateY(10px) rotate(45deg);
  }

  &.open .line:nth-child(2) {
    opacity: 0;
  }

  &.open .line:nth-child(3) {
    transform: translateY(-10px) rotate(-45deg);
  }
}
</style>
