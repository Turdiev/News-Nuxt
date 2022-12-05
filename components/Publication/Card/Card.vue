<template>
  <div class="Card">
    <div class="Card__wrapper">
      <div class="flex">
        <div class="Card__time">
          <span>{{ news.time }}</span>
        </div>
        <div
          v-if="isTablet"
          class="Card__city"
        >
          <span>{{ news.city }}</span>
        </div>
      </div>
      <div class="Card__info">
        <div class="Card__title">
          <n-link
            :to="`/news/${ date + '+' +index}`"
          >
            <span>{{ news.title }}</span>
          </n-link>
        </div>
        <div class="Card__text">
          <span>{{ news.text }}</span>
        </div>
        <div
          v-if="!isTablet"
          class="Card__city"
        >
          <span>{{ news.city }}</span>
        </div>
      </div>
    </div>
    <div class="Card__line" />
  </div>
</template>

<script>
export default {
  name: 'PCard',

  props: {
    news: {
      type: Object,
      default: () => {}
    },
    index: Number,
    date: String
  },

  computed: {
    isTablet() {
      return window.innerWidth < 992
    }
  }
}
</script>

<style lang="scss" scoped>
.Card {
  width: 100%;

  &__wrapper {
    display: flex;
    justify-content: space-between;

    @media screen and (max-width: 992px) {
      flex-direction: column;
    }
  }

  &__time {
    width: 49px;
    height: 22px;
    background: #EEF0F3;
    border-radius: 20px;
    padding: 0 10px;

    @media screen and (max-width: 992px) {
      margin-right: 20px;
    }

    & span {
      font-weight: 700;
      font-size: 12px;
      line-height: 22px;
      text-transform: uppercase;
      color: #5083F3;
    }
  }

  &__info {
    margin-left: 60px;

    @media screen and (max-width: 992px) {
      margin-left: 0;
    }
  }

  &__title {
    margin-bottom: 8px;

    & span {
      font-weight: 700;
      font-size: 18px;
      line-height: 24px;
      color: #000000;
    }
  }

  &__text {
    margin-bottom: 8px;

    & span {
      font-weight: 400;
      font-size: 16px;
      line-height: 24px;
      color: #000000;
    }
  }

  &__city {
    margin-bottom: 8px;

    & span {
      font-weight: 700;
      font-size: 12px;
      line-height: 22px;
      text-transform: uppercase;
      color: #B4C0CF;
    }
  }

  &__line {
    width: 400px;
    height: 1px;
    left: 0px;
    bottom: 0px;
    background: #DCE2EA;

    @media screen and (max-width: 568px) {
      width: 100%;
    }
  }
}
</style>
