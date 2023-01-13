<template>
  <div class="container">
    <nav>
      <h1 class="white--text nav-title">Личный кабинет</h1>
        <v-tabs flat dark slider-color="#5181B8" background-color="#1D1625" color="white" class="tabs">
          <v-tab>Личная информация</v-tab>
          <v-tab>Лестница подарков</v-tab>
          <v-tab>Обучение по сервису</v-tab>
          <v-tab>Программа лояльности</v-tab>
          <v-tab>Реферальная программа</v-tab>
          <v-tab>Подключение магазина</v-tab>
        </v-tabs>
    </nav>
    <div class="page-content">
      <LevelsSection />
      <ServicesSection />
      <PromoSection />
    </div>
  </div>
</template>

<script>
import ServicesSection from "@/components/ServicesSection.vue";
import PromoSection from "@/components/PromoSection.vue";
import LevelsSection from "@/components/LevelsSection.vue";

export default {
  components: {LevelsSection, PromoSection, ServicesSection}
}
</script>

<style lang="scss">
  .container {
    margin: 38px 35px 50px 35px;
    padding: 0;
  }

  .v-slide-group__prev {
    display: none !important;
  }

  .v-tab {
    padding: 0;
    font-size: 15px;
    font-weight: 400;
    text-transform: none !important;
    line-height: 20px;
    letter-spacing: -0.24px;
    margin-right: 32px;
  }

  .nav-title {
    margin-bottom: 20px;
    font-size: 24px;
    font-weight: 400;
  }

  .page-content {
    width: 100%;
    margin-top: 30px;
    & > * {
      margin-bottom: 50px;
    }
  }

  //.tabs {
  //  max-width: 1120px;
  //}
</style>