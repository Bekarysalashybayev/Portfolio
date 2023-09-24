<template>
  <div class="title">Technologies</div>
  <div class="t-main">
    <div class="item" v-for="(el, i) in main_tech" :key="i">
      <div class="name">{{ el.name }}</div>
      <div class="level">{{ getLevelName(el.level) }}</div>
      <div class="range">
        <div class="range-inner" :style="{ '--r-width': `${(el.level / 5) * 100}%` }"></div>
      </div>
    </div>
  </div>
  <div class="title s-title">Additional technologies and skills</div>

  <div class="t-add">
    <ul>
      <li v-for="t in techs" :key="t">{{ t }}</li>
    </ul>
  </div>
</template>
<script setup lang="ts">
import { onMounted, ref } from 'vue'

onMounted(() => {
  const box = document.querySelector('.t-main')

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          box?.classList.add('ranged')
          // box?.style.opacity = '1'
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.2 }
  )

  if (box) {
    observer.observe(box)
  }
})

const main_tech = ref<
  {
    name: string
    level: number
  }[]
>([
  {
    name: 'Python',
    level: 4
  },
  {
    name: 'JavaScript, TypeScript',
    level: 5
  },
  {
    name: 'Java',
    level: 3
  },
  {
    name: 'React js',
    level: 4
  },
  {
    name: 'React native',
    level: 4
  },
  {
    name: 'Vue js, Nuxt js',
    level: 5
  },
  {
    name: 'Django, DRF, Django ORM',
    level: 4
  },
  {
    name: 'Spring Framework, Spring Boot',
    level: 4
  },
  {
    name: 'Html5',
    level: 5
  },
  {
    name: 'CSS3, Sass, Scss',
    level: 5
  },
  {
    name: 'PL/SQL',
    level: 3
  },
  {
    name: 'SQL (MySQL, PostgreSQL)',
    level: 4
  }
])

const techs = ref([
  'Git',
  'Docker',
  'Teamwork',
  'Bootstrap',
  'Vuetify',
  'Axios',
  'Math',
  'CI/CD',
  'Rest API',
  'Vuex',
  'Pinia',
  'Storybook',
  'Nginx',
  'Pm2',
  'Gunicorn',
  'Celery',
  'Charts (Apex, Plotly, ...)',
  'Webpack',
  'Vite',
  'Gulp'
])

const getLevelName = (level: number) => {
  if (level === 4) return 'Regular'
  if (level === 3) return 'Middle'
  if (level === 2) return 'Beginner'
  return 'Advanced'
}
</script>
<style scoped lang="scss">
@use '@/assets/scss/colors' as *;
@use '@/assets/scss/breakpoints' as *;

.title {
  font-size: 4rem;
  line-height: 1;
  font-weight: 600;
  margin-bottom: 5rem;
}

.s-title {
  font-size: 2.5rem;
}

.t-main {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 3rem;
  margin-bottom: 10rem;

  .item {
    width: 100%;
    max-width: 1024px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    line-height: 1;
    font-size: 1.4rem;
    color: $color-4;

    .name {
      color: $color-3;
      font-size: 1.6rem;
    }

    .range {
      margin-top: 0.6rem;
      width: 100%;
      height: 2rem;
      background-color: $color-5;
      border-radius: 1rem;

      &-inner {
        background: linear-gradient(to left, #13adc7, #6978d1, #945dd6);
        border-radius: 1rem;
        height: 100%;
        width: 0;
        transition: width linear 1s;
      }
    }
  }

  &.ranged .range-inner {
    width: var(--r-width);
  }
}

.t-add {
  margin-bottom: 20rem;
  font-size: 2rem;
  font-weight: 550;

  ul {
    width: 100%;
    max-width: 1024px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 3rem;

    li {
      width: calc(25% - 3rem);
    }
  }

  @media screen and (max-width: $tab-1) {
    margin-bottom: 10rem;
    ul li {
      width: calc(33% - 3rem);
    }
  }

  @media screen and (max-width: $phone-4) {
    ul li {
      width: calc(50% - 1.5rem);
    }
  }
}
</style>
