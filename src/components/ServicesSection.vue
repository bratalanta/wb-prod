<template>
  <section class="services">
    <h2 class="services__title text-h6">До получения следующего уровня осталось немного</h2>
    <div class="services__cards">
      <ServiceCard />
      <ServiceCard />
      <ServiceCard />
    </div>
  </section>
</template>

<script>
import ServiceCard from "@/components/ServiceCard.vue";

export default {
  components: {ServiceCard},
  computed: {
    cardWidth() {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs': return "100%"
        case 'sm': return "45%"
        default: return 200
      }
    },
  }
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
      margin-right: -20px;
    }
  }

</style>