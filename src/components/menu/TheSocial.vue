<template>
  <div class="social">
    <a href="https://github.com/Bekarysalashybayev" target="_blank">
      <git-icon />
    </a>

    <a href="https://www.linkedin.com/in/bekarys-alashybaev-155862158" target="_blank">
      <in-icon />
    </a>

    <a href="#" target="_blank">
      <h-h-icon />
    </a>
  </div>
</template>

<script setup lang="ts">
import GitIcon from '@/components/icons/GitIcon.vue'
import InIcon from '@/components/icons/InIcon.vue'
import HHIcon from '@/components/icons/HHIcon.vue'
</script>

<style scoped lang="scss">
.social {
  display: flex;
  align-items: center;
  gap: 3rem;
}
</style>
