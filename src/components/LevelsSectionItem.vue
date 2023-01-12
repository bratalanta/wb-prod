<template>
  <article class="d-flex flex-column align-center level">
    <div class="mb-5">
      <LevelFulfilled :level="1"/>
    </div>
    <div class="level__price">10 000 ₽</div>
    <div class="level__text">Уровень 1</div>

    <v-tooltip right v-model="isTooltipDisplayed" content-class="tooltip-top">
      <template v-slot:activator="">
        <img src="../assets/level/gift-active.svg" class="level__gift" @click="isTooltipDisplayed = !isTooltipDisplayed" alt="">
      </template>
      <span>Удаление отзывов - 5 шт. <br> Лайки на бренд - 5 шт. <br> Лайки на товар - 5 шт.</span>
    </v-tooltip>

  </article>
</template>

<script>

import LevelFulfilled from "@/components/LevelFulfilled.vue";

export default {
  components: {LevelFulfilled},
  data() {
    return {
      isTooltipDisplayed: false
    }
  }
}
</script>

<style lang="scss" scoped>
  .level {
    z-index: 2;

    &__price {
      color: white;
      font-weight: 500;
      font-size: 16px;
      margin-bottom: 6px;
    }
    &__text {
      color: #D3D3D3;
      font-weight: 400;
      font-size: 12px;
      margin-bottom: 10px;
    }
    &__gift {
      height: 24px;
      width: 24px;
    }
  }
</style>