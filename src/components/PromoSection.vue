<template>
  <section class="promo">
    <h2 class="promo__title">У меня есть промокод</h2>
    <div class="promo__text">Введите промокод в поле ниже для получения бонусов</div>
    <v-form class="promo__form">
      <v-text-field v-model="promo" dense solo hide-details hide-spin-buttons background-color="#222C3C" flat dark class="promo__input"></v-text-field>
      <v-btn dark block color="#6A65FF" height="40" class="white--text font-weight-medium" :disabled="!promo">активировать</v-btn>
    </v-form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      promo: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.promo {
  &__title {
    font-weight: 400;
    font-size: 20px;
    color: white;
    margin-bottom: 8px;
  }
  &__form {
    max-width: 240px;

    & > * {
      margin-bottom: 10px;
    }
  }
  &__text {
    color: #808080;
    font-size: 16px;
    margin-bottom: 22px;
  }
  &__input {
    border: 1px solid #313D4F;
    font-size: 14px;
  }
}
</style>