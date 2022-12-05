<template>
  <div class="container">
    <BreadCrumbs />

    <div class="news__head">
      <div class="news__title">
        <h2> НОВОСТИ </h2>
      </div>
      <div class="news__select">
        <span>{{ titleSelect }}</span>
      </div>
    </div>

    <div class="news__content">
      <DividedPage class="inner">
        <template slot="content">
          <div class="publications">
            <Publication
              v-for="(news, i) in dataNews"
              :key="i"
              :data="news"
              class="publication"
            >
              <template slot="banner">
                <AdvertisingBanner v-if="i === 0 && !isMobile" />
                <AsideBanner v-if="i === 0 && isMobile" />
              </template>
            </Publication>
          </div>
        </template>
        <template slot="aside">
          <div v-if="!isTablet" class="card">
            <AsideBanner />
            <ButtonScrollUp />
          </div>
        </template>
      </DividedPage>
    </div>
  </div>
</template>

<script>
import DividedPage from '@/components/common/DividedPage.vue'
import Publication from '@/components/Publication/Publication.vue'
import AsideBanner from '@/components/Banners/AsideBanner.vue'
import AdvertisingBanner from '@/components/Banners/AdvertisingBanner.vue'
import ButtonScrollUp from '@/components/Buttons/ButtonScrollUp.vue'

export default {
  name: 'IndexPage',

  components: {
    DividedPage,
    Publication,
    AsideBanner,
    AdvertisingBanner,
    ButtonScrollUp
  },

  computed: {
    isMobile() {
      return window.innerWidth < 568
    },

    isTablet() {
      return window.innerWidth < 992
    },

    titleSelect() {
      return this.isMobile ? 'Выбрать город' : 'Город'
    },

    dataNews() {
      return this.$store.state.data
    }
  }
}
</script>

<style lang="scss" scoped>
.news {

  &__head {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin-top: 45px;

    @media screen and (max-width: 568px) {
      flex-direction: column;
      justify-content: start;
      align-items: start;
      margin-top: 30px;
      margin-bottom: 18px;
    }
  }

  &__title {
    & h2 {
      font-weight: 700;
      font-size: 24px;
      line-height: 38px;
      text-transform: uppercase;
      color: #000000;
    }

    @media screen and (max-width: 568px) {
      margin-bottom: 14px;
    }
  }

  &__select {
    position: relative;
    padding-right: 15px;

    & span {
      font-weight: 500;
      font-size: 16px;
      line-height: 26px;
      color: #000000;
    }

    &::after {
      content: "";
      width: 6px;
      height: 6px;
      border: solid #000;
      border-width: 1px 0 0 1px;
      transform: translate(-50%, -50%) rotate(-133deg);
      position: absolute;
      left: 92%;
      top: 50%;

      @media screen and (max-width: 568px) {
        transform: translate(-50%, -50%) rotate(130deg);
      }
    }
  }
}

.publications {
  margin-top: 40px;

  @media screen and (max-width: 568px) {
    margin-top: 22px;
  }
}

.publication {
  margin-bottom: 60px;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-end;
  height: calc(100% - 160px);
  margin-top: 100px;
}
</style>
