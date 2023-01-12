<template>
    <v-card min-width="200" min-height="250" class="card d-flex flex-column" color="#1B1E2D" flat>
      <h3 class="card__title">10 автоответов</h3>
      <div class="card__subtitle">3₽ / штука</div>
      <v-card class="inner-card" flat color="#232633">
        <div class="inner-card__text">Срок использования</div>
        <div class="inner-card__date">2 месяцев</div>
        <div class="d-flex justify-space-between align-center">
          <div class="inner-card__bonuses">Бонусы</div>
          <div>
            <v-icon class="mr-3" color="#295A87">mdi-thumb-up</v-icon>
            <v-icon color="#295A87">mdi-wallet</v-icon>
          </div>
        </div>
      </v-card>
      <v-card-actions class="pa-0">
        <v-btn block color="#6A65FF" height="40" class="white--text font-weight-medium">купить за 30₽</v-btn>
      </v-card-actions>
    </v-card>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
  .card {
    padding: 10px;
    margin-right: 20px;

    &__title {
      color: white;
      font-weight: 700;
      font-size: 20px;
      margin-bottom: 4px;
    }

    &__subtitle {
      color: #6A65FF;
      font-weight: 400;
      font-size: 16px;
      margin-bottom: 18px;
    }
  }

  .inner-card {
    padding: 11px 16px 11px 13px;
    margin-bottom: 27px;

    &__text {
      color: #808080;
      font-weight: 400;
      font-size: 12px;
      margin-bottom: 4px;
    }
    &__date {
      color: white;
      font-weight: 400;
      font-size: 16px;
      margin-bottom: 15px;
    }
    &__bonuses {
      color: #808080;
      font-weight: 400;
      font-size: 10px;
      text-transform: uppercase;
    }
  }
</style>