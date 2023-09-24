<template>
  <div class="main" id="main">
    <div class="container">
      <div class="title">Bekarys Alashybayev</div>
      <div class="subtitle">
        Hello there! I'm Bekarys, a passionate and creative frontend developer with a keen eye for
        design and a love for crafting exceptional user experiences. With 4 years of experience in
        the industry, I've had the privilege of working on diverse projects that have honed my
        skills and allowed me to grow as a developer.
      </div>
      <be-button class="btn" @click="goTo('project')"> Let's begin</be-button>
    </div>
    <main-bg-icon class="icon" />
  </div>
</template>

<script setup lang="ts">
import BeButton from '@/components/ui/BeButton.vue'
import MainBgIcon from '@/components/icons/MainBgIcon.vue'

const goTo = (name: string) => {
  const element = document.getElementById(name)

  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  } else {
    console.error(`Element with ID ${name} not found.`)
  }
}
</script>

<style scoped lang="scss">
@use '@/assets/scss/breakpoints' as *;

.main {
  padding: 5rem 0;
  position: relative;

  .container {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .title {
    font-size: 4rem;
    line-height: 5rem;
    margin-bottom: 3rem;
  }

  .subtitle {
    font-size: 2rem;
    line-height: 3rem;
    font-weight: 200;
    margin-bottom: 4rem;
    max-width: 100rem;
  }

  .btn {
    width: 17.8rem;
  }

  .icon {
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: -1;
  }

  @media screen and (min-width: $mobile) {
    min-height: 500px;
    height: calc(100vh - 12rem);
  }
}
</style>
