<template>
  <section :class="['levels', smAndUp]">
    <div class="d-flex justify-space-between pb-6">
      <h1 class="levels__title">Ваш текущий уровень: 1</h1>
      <a
          href="https://docs.google.com/document/d/1rzajIm88wVQsHPZORBkLx5LIKAvKOFMGHwFT0eLJAu4/edit"
          class="levels__link"
          target="_blank"
      >Условия программы лояльности</a>
    </div>
    <v-card color="#261F2E" flat :class="['levels__card', smAndUp]">
      <LevelsSectionItem v-for="i in 5" :key="i" :levelNumber="i"/>
    </v-card>
  </section>
</template>
<script>
import LevelsSectionItem from "@/components/LevelsSectionItem.vue";

export default {
  components: {LevelsSectionItem},
  computed: {
    smAndUp() {
      if (this.$vuetify.breakpoint.smAndUp) {
        return 'md-size'
      }

      return null
    },
  }
}
</script>

<style lang="scss" scoped>
  @mixin progress-bar {
    content: '';
    position: absolute;
    height: 3px;
    border-radius: 9px;

    top: 50px;
    left: 5%;
  }

  .levels {
    max-width: 895px;

    &__card {
      position: relative;
      border-radius: 8px;
      padding: 20px;
      display: flex;
      justify-content: space-between;
      flex-direction: column;
      height: 1000px;

      &.md-size {
        flex-direction: row;
        height: 100%;

        position: relative;

        &::after {
          @include progress-bar;
          width: 88%;
          background: rgba(34, 44, 60, 1);
          z-index: 1;
        }

        &::before {
          @include progress-bar;
          width: 17%;
          background: rgba(106, 101, 255, 1);
          z-index: 2;
        }
      }
    }

    &__title {
      font-size: 20px;
      font-weight: 400;
      color: white;
      padding-right: 30px;
    }

    &__link {
      text-align: right;
      font-weight: 400;
      font-size: 16px;
      color: #6A65FF;
      text-decoration: none;
    }
  }
</style>