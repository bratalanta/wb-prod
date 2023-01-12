<template>
  <svg width="56" height="62" viewBox="0 0 56 62" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M32.25 3.18579L49.9628 13.4123C52.5927 14.9307 54.2128 17.7367 54.2128 20.7735V41.2265C54.2128 44.2633 52.5927 47.0693 49.9628 48.5877L32.25 58.8142C29.6201 60.3326 26.3799 60.3326 23.75 58.8142L6.03719 48.5877C3.40728 47.0693 1.78719 44.2633 1.78719 41.2265V20.7735C1.78719 17.7367 3.40728 14.9307 6.03719 13.4123L23.75 3.18579C26.3799 1.66741 29.6201 1.66741 32.25 3.18579Z" fill="#6A65FF" stroke="#8B87FF" stroke-width="3"/>
    <text x="20" y="38" fill="white" font-weight="700" font-size="24" font-style="inherit">{{ level }}</text>
  </svg>

</template>

<script>
export default {
  props: {
    level: {
      type: Number
    }
  }
}
</script>

<style lang="scss" scoped>
</style>