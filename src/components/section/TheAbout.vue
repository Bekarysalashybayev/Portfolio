<template>
  <div class="title">About me</div>

  <div class="about">
    <div class="item">
      <div class="year">
        2019
        <div class="dot"></div>
      </div>
      <div class="text">
        <strong>Freelance</strong>
        <br />
        Fullstack developer
        <br />
        Development of a web project. Development and maintenance of a web application using Vue.js
        and Nuxt.js. Development and maintenance of an API using Django and Django REST framework.
      </div>
    </div>
    <div class="item">
      <div class="year">
        2020
        <div class="dot"></div>
      </div>
      <div class="text">
        <strong>TOO "ON MONDAY"</strong>
        <br />
        Fullstack developer
        <br />
        Web Studio. Development of a web project. Development and maintenance of a web application
        using Vue.js and Nuxt.js. Development and maintenance of an API using Django and Django REST
        framework.
      </div>
    </div>
    <div class="item">
      <div class="year">
        2021-2022
        <div class="dot"></div>
      </div>
      <div class="text">
        <strong>Samruk Business Academy</strong>
        <br />
        Fullstack developer
        <br />
        Development and maintenance of a web application using Vue.js and Nuxt.js. Development and
        maintenance of an API using Django and Django REST framework. Development of admin
        panels/dashboards, data collection and display of summaries across different time periods.
      </div>
    </div>
    <div class="item">
      <div class="year">
        2023 - Present
        <div class="dot"></div>
      </div>
      <div class="text">
        <strong>Евразийский банк, АО</strong>
        <br />
        Frontend-разработчик
        <br />
        Development and maintenance of a web application using Vue.js for online auto loans and
        consumer credit. Product support, development, and optimization. Migration of projects from
        Vue 2 to Vue 3. Development of internal projects for product management and information
        gathering (Admin panels, Dashboards).
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
@use '@/assets/scss/colors' as *;
@use '@/assets/scss/breakpoints' as *;

.title {
  font-size: 4rem;
  line-height: 1;
  font-weight: 600;
  margin-bottom: 5rem;
}

.about {
  display: flex;

  .item {
    width: 25%;

    font-size: 1.8rem;
    line-height: 1.4;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;

    .text {
      max-width: 90%;
    }

    &:first-child .year:before,
    &:last-child .year:after {
      display: none;
    }

    .year {
      position: relative;
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      line-height: 1;
      padding-bottom: 3rem;
      margin-bottom: 1rem;

      &:after,
      &:before {
        content: '';
        width: 50%;
        height: 1rem;
        background-color: $color-3;
        position: absolute;
        bottom: 0.5rem;
      }

      &:after {
        left: 50%;
      }

      &:before {
        left: 0;
      }

      .dot {
        width: 2rem;
        height: 2rem;
        background-color: $color-3;
        border-radius: 50%;
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
      }
    }
  }

  @media screen and (max-width: calc($desktop-1 - 1px)) {
    flex-direction: column;

    .item {
      width: 100%;
      align-items: flex-start;
      position: relative;
      padding-left: 4rem;

      .year {
        position: static;
        width: max-content;
        display: block;
        padding-bottom: 0;
        margin-bottom: 1rem;

        &:after,
        &:before {
          content: '';
          width: 1rem;
          height: 50%;
          background-color: $color-3;
          position: absolute;
          left: 0.5rem;
        }

        &:after {
          top: 50%;
        }

        &:before {
          top: 0;
        }

        .dot {
          width: 2rem;
          height: 2rem;
          background-color: $color-3;
          border-radius: 50%;
          position: absolute;
          top: 50%;
          left: 0;
          transform: translate(0, -50%);
        }
      }

      .text {
        max-width: 100%;
        width: 100%;
        margin-bottom: 2rem;
        text-align: left;
      }
    }
  }
}
</style>
