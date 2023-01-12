<template>
  <v-app>
    <v-main class="main">
      <GiftLadderView/>
    </v-main>
  </v-app>
</template>

<script>
import GiftLadderView from "@/views/GiftLadderView.vue";

export default {
  name: 'App',
  components: {
    GiftLadderView,
  }
};
</script>

<style lang="scss">
  .main {
    background: #1D1625;
  }
</style>