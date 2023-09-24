<template>
  <the-main />
  <div class="container">
    <div id="project">
      <the-project />
    </div>
    <div id="technologies">
      <the-technology />
    </div>
    <div id="about">
      <the-about />
    </div>
  </div>
</template>

<script setup lang="ts">
import TheMain from '@/components/section/TheMain.vue'
import TheProject from '@/components/section/TheProject.vue'
import TheTechnology from '@/components/section/TheTechnology.vue'
import TheAbout from '@/components/section/TheAbout.vue'
</script>
