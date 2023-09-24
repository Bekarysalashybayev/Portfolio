<template>
  <header>
    <div class="container">
      <nav>
        <the-logo class="n-logo mobile" @click="goTo('main')" />
        <burger-button class="mobile" @click="isOpen = !isOpen" />
        <div :class="['nav-inner', isOpen && 'open']">
          <the-logo class="n-logo desktop" @click="goTo('main')" />
          <ul>
            <li @click="goTo('project')">Projects</li>
            <li @click="goTo('technologies')">Technologies</li>
            <li @click="goTo('about')">About me</li>
          </ul>
          <the-social class="social" />
        </div>
      </nav>
    </div>
  </header>
</template>

<script setup lang="ts">
import TheLogo from '@/components/ui/TheLogo.vue'
import TheSocial from '@/components/menu/TheSocial.vue'
import BurgerButton from '@/components/ui/BurgerButton.vue'
import { computed, ref, watch } from 'vue'
import { useWindowSize } from '@vueuse/core'

const isOpen = ref(false)

const { width } = useWindowSize()
const MOBILE_SIZE = ref(767)
const isMobile = computed(() => {
  return width.value < MOBILE_SIZE.value
})

watch(
  () => isOpen.value,
  (value: boolean) => {
    if (value && isMobile.value) {
      document.body.style.overflow = 'hidden'
    } else {
      document.body.style.overflow = 'auto'
    }
  }
)

const goTo = (name: string) => {
  const element = document.getElementById(name)
  let closed = false

  if (isMobile.value) {
    isOpen.value = false
    closed = true
  }

  if (element) {
    if (isMobile.value && closed) {
      setTimeout(() => {
        element.scrollIntoView({ behavior: 'smooth' })
      }, 600)
    } else {
      element.scrollIntoView({ behavior: 'smooth' })
    }
  } else {
    console.error(`Element with ID ${name} not found.`)
  }
}
</script>

<style scoped lang="scss">
@use '@/assets/scss/colors' as *;
@use '@/assets/scss/breakpoints' as *;

header {
  position: sticky;
  top: 0;
  width: 100%;
  background-color: $color-1;
  border-bottom: 2px solid $color-2;
  z-index: 9999;
  height: 10.2rem;
  display: flex;
  align-items: center;

  .mobile {
    display: none;
  }

  nav,
  .nav-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
    font-size: 2rem;
    line-height: 1;

    ul {
      display: flex;
      align-items: center;
      list-style: none;

      gap: 4rem;

      li {
        cursor: pointer;
      }
    }
  }

  .nav-inner {
    flex: 0 0 100%;
  }

  @media screen and (max-width: calc($mobile - 1px)) {
    .mobile {
      display: block;
    }

    .desktop {
      display: none !important;
    }

    .logo {
      display: flex;
    }

    .nav-inner {
      position: fixed;
      top: 10.2rem;
      left: -100%;
      bottom: 0;
      width: 100%;
      background-color: $color-1;
      padding: 3rem 0;

      flex-direction: column;
      justify-content: unset;
      overflow-y: auto;
      overflow-x: hidden;
      transition: left linear 0.6s;

      &.open {
        left: 0;
      }

      ul {
        flex-direction: column;
      }

      .social {
        margin-top: auto;
      }
    }
  }
}
</style>
