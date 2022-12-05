<template>
  <div class="AdvertisingBanner">
    <p class="AdvertisingBanner__text">
      Рекламный баннер
    </p>
  </div>
</template>

<script>
export default {
  name: 'AdvertisingBanner'
}
</script>

<style lang="scss" scoped>
.AdvertisingBanner {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 160px;
  border: 1px solid #000000;
  margin-bottom: 20px;

  &__text {
    font-weight: 700;
    font-size: 18px;
    line-height: 24px;
    text-align: center;
    color: #000000;
  }
}
</style>
