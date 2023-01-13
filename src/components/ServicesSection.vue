<template>
  <section class="services">
    <h2 class="services__title text-h6">До получения следующего уровня осталось немного</h2>
    <div class="services__cards">
      <ServiceCard v-for="i in 3" :cardNumber="i" :key="i"/>
    </div>
  </section>
</template>

<script>
import ServiceCard from "@/components/ServiceCard.vue";

export default {
  components: {ServiceCard},
}
</script>

<style lang="scss" scoped>
  .services {

    &__title {
      font-weight: 400;
      color: white;
      margin-bottom: 24px;
    }

    &__cards {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
    }
  }
</style>