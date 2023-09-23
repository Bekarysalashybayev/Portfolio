<template>
  <div class="title">Projects</div>
  <div class="projects">
    <div class="project" v-for="i in 4" :key="i">
      <div class="img"></div>
      <div class="name">
        Project {{ i }}
        <div class="line"></div>
      </div>
      <div class="text">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias aut dolor ducimus eum fugit,
        nam nemo nostrum nulla odio porro provident quam reprehenderit voluptatem. Ad enim eum non
        placeat ut. Aliquid at atque, dicta expedita illo illum iusto laborum maiores minima
      </div>
      <be-button>Look it up</be-button>
    </div>
  </div>
</template>
<script setup lang="ts">
import BeButton from '@/components/ui/BeButton.vue'
</script>

<style scoped lang="scss">
@use '@/assets/scss/colors' as *;

.title {
  font-size: 4rem;
  line-height: 1;
  font-weight: 600;
  margin-bottom: 5rem;
}

.projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-bottom: 10rem;
  gap: 4rem;

  .project {
    width: 100%;
    max-width: 50rem;
    padding: 3rem 2rem 2rem 2rem;
    box-shadow: 2px 2px 10px 2px rgba(255, 255, 255, 0.4);
    border-radius: 5rem 0 5rem 0;

    .name {
      font-size: 2rem;
      text-transform: uppercase;
      width: max-content;
      padding-bottom: 0.5rem;
      margin: 0 auto 1.5rem;
      position: relative;

      .line {
        position: absolute;
        top: 100%;
        left: -2rem;
        width: calc(100% + 4rem);
        height: 2px;
        background: linear-gradient(to left, #13adc7, #6978d1, #945dd6);
      }
    }

    .text {
      font-size: 1.6rem;
      margin-bottom: 2rem;
    }

    .img {
      width: 100%;
      height: 26.6rem;
      background-color: $color-3;
      border-radius: 1rem;
      overflow: hidden;
      margin-bottom: 2rem;

      img {
        width: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
