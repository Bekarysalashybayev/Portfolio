<template>
  <div class="wrapper">
    <the-header />
    <RouterView />
    <the-footer />
  </div>
</template>

<script setup lang="ts">
import TheHeader from '@/components/menu/TheHeader.vue'
import TheFooter from '@/components/menu/TheFooter.vue'
</script>

<style scoped></style>
