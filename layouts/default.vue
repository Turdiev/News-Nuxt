<template>
  <div class="main">
    <TheHeader />
    <div class="dividing-line" />

    <nuxt />

    <TheFooter />
  </div>
</template>

<script>
import TheHeader from '@/components/TheHeader.vue'
import TheFooter from '@/components/TheFooter.vue'

export default {
  components: {
    TheHeader,
    TheFooter
  }
}
</script>

<style lang="scss" scoped>
  .dividing-line {
    width: 100vw;
    height: 10px;
    background: #000;
  }
</style>
