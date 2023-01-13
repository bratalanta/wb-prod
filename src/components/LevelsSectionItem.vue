<template>
  <article class="d-flex flex-column align-center level">
    <div
        :class="[
            'mb-1', 'mb-md-5', {'level__polygon': levelNumber === 1 || levelNumber === 5},
            {'level__vertical-bar': levelNumber === 1 && !smAndUp},
            {'level__polygon-bar': levelNumber === 1 && smAndUp}
            ]">
      <LevelFulfilled :level="levelNumber" v-if="levelNumber === 1"/>
      <img src="../assets/level/next.svg" alt="" v-else-if="levelNumber === 2">
      <img src="../assets/level/default.svg" alt="" v-else>
    </div>
    <div class="level__price">{{levelPrice[levelNumber]}} ₽</div>
    <div class="level__text">Уровень {{ levelNumber }}</div>
    <v-tooltip :max-width="!smAndUp ? '150' : '100%'" right v-model="isTooltipDisplayed" :open-on-hover="false" v-if="levelNumber === 1">
      <template v-slot:activator="{on}" >
        <img v-click-outside="hide" src="../assets/level/gift-active.svg" class="level__gift" v-on.self="on" @click.self="isTooltipDisplayed = !isTooltipDisplayed" alt="">
      </template>
      <span>Удаление отзывов - 5 шт. <br> Лайки на бренд - 5 шт. <br> Лайки на товар - 5 шт.</span>
    </v-tooltip>
    <img src="../assets/level/gift.svg" class="level__gift" alt="" v-else>
  </article>
</template>
<script>
import LevelFulfilled from "@/components/LevelFulfilled.vue";
import ClickOutside from 'vue-click-outside'

export default {
  components: {LevelFulfilled},
  props: {
    levelNumber: {
      levelNumber: {
        type: Number
      }
    }
  },
  methods: {
    hide() {
      this.isTooltipDisplayed = false
    }
  },
  directives: {
    ClickOutside
  },
  data() {
    return {
      isTooltipDisplayed: false,
      levelPrice: {
        1: '10 000',
        2: '15 000',
        3: '20 000',
        4: '30 000',
        5: '50 000'
      }
    }
  },
  computed: {
    smAndUp() {
      return this.$vuetify.breakpoint.smAndUp
    },
  }
}
</script>

<style lang="scss" scoped>
@mixin progress-bar-sm {
  content: '';
  position: absolute;
  width: 3px;
  border-radius: 9px;

  top: 65px;
  left: 27px;
}

.popper {
  z-index: 5;
  background: rgba(116, 130, 155, 0.55);
  backdrop-filter: blur(9px);
  border: none;

  &__arrow {
    background: rgba(116, 130, 155, 0.55);
    width: 100px;
    border-color: transparent transparent transparent rgba(116, 130, 155, 0.55);
  }
}

.arrow {
  width: 100px;
}

.popper .popper__arrow {
  border-color: transparent transparent transparent rgba(116, 130, 155, 0.55);
  width: 100px;
}

.v-tooltip__content {
  content: initial;
  overflow: visible;
  background: rgba(116, 130, 155, 0.55);
  backdrop-filter: blur(9px);
  opacity: 1;

  &::after {
    content: '';
    z-index: -1;
    position: absolute;
    width: 13px;
    height: 13px;
    top: 43%;
    left: -1%;
    background: rgb(81,85,106);
    transform: rotate(45deg);
  }
}
.level {
  z-index: 2;

  &__polygon {
    position: relative;

    &::before {
      z-index: -1;
      position: absolute;
      content: '';
      left: -3px;
      width: 65px;
      height: 65px;
      background-color: rgba(38, 31, 46, 1);
    }
  }

  &__price {
    color: white;
    font-weight: 500;
    font-size: 16px;
    margin-bottom: 6px;
    background-color: rgba(38, 31, 46, 1);
  }
  &__text {
    color: #D3D3D3;
    font-weight: 400;
    font-size: 12px;
    margin-bottom: 10px;
    background-color: rgba(38, 31, 46, 1);
  }
  &__gift {
    height: 24px;
    width: 24px;
  }

  &__vertical-bar {
    position: relative;

    &::after {
      @include progress-bar-sm;
      height: 737px;
      background: rgba(34, 44, 60, 1);
      z-index: -2;
    }

    &::before {
      @include progress-bar-sm;
      height: 121px;
      background: rgba(106, 101, 255, 1);
      z-index: -1;
    }
  }
}
</style>