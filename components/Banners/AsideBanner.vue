<template>
  <div class="AsideBanner">
    <div class="AsideBanner__badge">
      <span>РЕКЛАМА</span>
    </div>
    <div class="AsideBanner__footer">
      <div class="AsideBanner__footer-title">
        <span>Insider park </span>
      </div>
      <div class="AsideBanner__footer-title _font-size">
        <span>Жилой район в Москве</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AsideBanner'
}
</script>

<style lang="scss" scoped>
.AsideBanner {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
  width: 320px;
  height: 380px;
  background: url('/images/banner.png');
  background-repeat: no-repeat;
  background-size: cover;

  @media screen and (max-width: 568px) {
    width: 328px;
    margin-bottom: 20px;
  }

  &__badge {
    width: 57px;
    height: 16px;
    background: rgba(0, 0, 0, 0.2);
    border-radius: 10px;
    padding: 0px 5px;
    margin: 12px 0 0 12px;
    gap: 10px;

    & span {
      font-weight: 400;
      font-size: 9px;
      line-height: 20px;
      text-align: center;
      letter-spacing: 0.05em;
      color: #FFFFFF;
    }
  }

  &__footer {
    width: 100%;
    height: 100px;
    background: rgba(128, 128, 128, 0.7);
    backdrop-filter: blur(5px);
    padding: 20px 0 0 20px;

    &-title {
      & span {
        font-weight: 700;
        font-size: 16px;
        line-height: 26px;
        color: #FFFFFF;
      }

      &._font-size {
        margin-top: 6px;

        & span {
          font-size: 18px;
        }
      }
    }
  }
}
</style>
