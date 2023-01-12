<template>
  <section class="levels">
    <div class="d-flex justify-space-between pb-6">
      <h1 class="levels__title">Ваш текущий уровень: 1</h1>
      <a
          href="https://docs.google.com/document/d/1rzajIm88wVQsHPZORBkLx5LIKAvKOFMGHwFT0eLJAu4/edit"
          class="levels__link"
          target="_blank"
      >Условия программы лояльности</a>
    </div>
    <v-card color="#261F2E" flat class="levels__card">
      <LevelsSectionItem />
      <LevelsSectionItem />
      <LevelsSectionItem />
      <LevelsSectionItem />
      <LevelsSectionItem />
      <v-progress-linear color="#6A65FF" background-color="#222C3C" value="15" height="3" rounded absolute class="progress-bar"/>
    </v-card>
  </section>
</template>

<script>

import LevelsSectionItem from "@/components/LevelsSectionItem.vue";

export default {
  components: {LevelsSectionItem},
}
</script>

<style lang="scss" scoped>
  .levels {
    max-width: 895px;

    &__card {
      position: relative;
      border-radius: 8px;
      padding: 20px;
      display: flex;
      justify-content: space-between;
    }

    &__title {
      font-size: 20px;
      font-weight: 400;
      color: white;
    }

    &__link {
      font-weight: 400;
      font-size: 16px;
      color: #6A65FF;
      text-decoration: none;
    }
  }

  .progress-bar {
    width: 81%;
    top: 24%;
    z-index: 1;
    left: 9.5%;
  }
</style>