<template>
  <section class="services">
    <h2 class="services__title">До получения следующего уровня осталось немного</h2>
    <div class="d-flex">
      <ServiceCard />
      <ServiceCard />
      <ServiceCard />
    </div>
  </section>
</template>

<script>
import ServiceCard from "@/components/ServiceCard.vue";

export default {
  components: {ServiceCard}

}
</script>

<style lang="scss" scoped>
.services {
  &__title {
    font-weight: 400;
    font-size: 20px;
    color: white;
    margin-bottom: 24px;
  }
}

</style>