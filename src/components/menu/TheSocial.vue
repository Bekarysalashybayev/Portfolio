<template>
  <div class="social">
    <a href="https://github.com/Bekarysalashybayev" aria-label="git" target="blank">
      <git-icon />
    </a>

    <a
      href="https://www.linkedin.com/in/bekarys-alashybaev-155862158"
      aria-label="linkedin"
      target="blank"
    >
      <in-icon />
    </a>

    <a
      href="https://hh.kz/resume/7ad824c5ff05b690e40039ed1f325857616262"
      aria-label="hh"
      target="blank"
    >
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
