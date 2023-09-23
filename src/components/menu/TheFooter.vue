<template>
  <div class="container">
    <footer>
      <div class="detail">
        Call me
        <a href="tel:+77472853499"> +7-747-285-3499 </a>
      </div>
      <div class="detail">
        Email
        <a href="mailto:bekarysalashybaev@gmail.com"> bekarysalashybaev@gmail.com </a>
      </div>
      <the-social class="social" />
    </footer>
  </div>
</template>

<script setup lang="ts">
import TheSocial from '@/components/menu/TheSocial.vue'
</script>

<style scoped lang="scss">
@use '@/assets/scss/colors' as *;
@use '@/assets/scss/breakpoints' as *;

footer {
  display: flex;
  align-items: center;
  padding: 20rem 0 5rem;

  .detail {
    font-size: 2.4rem;
    flex-grow: 1;

    a {
      margin-top: 1.5rem;
      font: inherit;
      color: inherit;
      display: block;
      font-weight: 550;

      &:hover {
        text-decoration: underline !important;
      }
    }
  }

  @media screen and (max-width: $mobile) {
    flex-direction: column;
    align-items: flex-start;
    padding-top: 10rem;

    a {
      display: inline-block !important;
      margin: 0 0 0 2rem;
    }

    .social {
      margin-top: 5rem;
    }
  }
}
</style>
