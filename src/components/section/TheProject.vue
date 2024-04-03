<template>
  <div class="title">Some of the Projects</div>
  <div class="projects">
    <div class="project">
      <div class="img">
        <img src="@/assets/img/project-1.png" alt="" />
      </div>
      <div class="name">
        testhub.kz
        <div class="line"></div>
      </div>
      <div class="text">
        Our site provides unique tasks, based on official standards. Increase your level of
        preparation, track progress and achieve high results. Exam confidence starts here!
      </div>
      <a href="https://testhub.kz/" target="blank">Look it up</a>
    </div>
    <div class="project">
      <div class="img">
        <img src="@/assets/img/project-2.png" alt="" />
      </div>
      <div class="name">
        ent.testhub.kz
        <div class="line"></div>
      </div>
      <div class="text">
        Our site provides unique tasks, based on official standards. Increase your level of
        preparation, track progress and achieve high results. Exam confidence starts here!
      </div>
      <a href="https://ent.testhub.kz/" target="blank">Look it up</a>
    </div>
    <div class="project">
      <div class="img">
        <img src="@/assets/img/project-3.png" alt="" />
      </div>
      <div class="name">
        koreanstreetfood.kz
        <div class="line"></div>
      </div>
      <div class="text">
        Our motto: «Healthy.Delicious.Easy.» It is important to us that the flavor and quality of
        our food is comfortable for our guests.
      </div>
      <a href="https://koreanstreetfood.kz/" target="blank">Look it up</a>
    </div>
    <div class="project">
      <div class="img">
        <img src="@/assets/img/project-4.png" alt="" />
      </div>
      <div class="name">
        juz40test.kz
        <div class="line"></div>
      </div>
      <div class="text">
        The #1 course that works for results. All subjects are taught by teachers who have become
        real specialists in their field.
      </div>
      <a href="https://koreanstreetfood.kz/" target="blank">Look it up</a>
    </div>
    <div class="project">
      <div class="img">
        <img src="@/assets/img/project-5.png" alt="" />
      </div>
      <div class="name">
        Corporate project
        <div class="line"></div>
      </div>
      <div class="text">Car with mileage on credit. Get approval online in 2 minutes</div>
      <a href="https://car.eubank.kz/ru" target="blank">Look it up</a>
    </div>
  </div>
</template>
<script setup lang="ts"></script>

<style scoped lang="scss">
@use '@/assets/scss/colors' as *;

.title {
  font-size: 4rem;
  line-height: 1;
  font-weight: 600;
  margin-bottom: 5rem;
}

a {
  font-size: 1.8rem;
  border: 0;
  color: inherit;
  background: linear-gradient(to left, #13adc7, #6978d1, #945dd6);
  width: max-content;
  border-radius: 2rem;
  padding: 1rem 2rem;
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
      margin-bottom: 3rem;
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
