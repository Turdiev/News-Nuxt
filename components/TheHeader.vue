<template>
  <div class="TheHeader">
    <div class="container">
      <div class="wrapper">
        <HeaderBurger />
        <TheLogo
          :show-label="true"
        />
        <HeaderSearch />
      </div>
    </div>
  </div>
</template>

<script>
import HeaderBurger from './TheHeader/HeaderBurger.vue'
import HeaderSearch from './TheHeader/HeaderSearch.vue'
import TheLogo from './TheLogo'

export default {
  name: 'TheHeader',

  components: {
    HeaderBurger,
    HeaderSearch,
    TheLogo
  },

  computed: {
    isMobile() {
      return window.innerWidth < 568
    }
  }
}
</script>

<style lang="scss" scoped>
  .TheHeader {
    width: 100%;
    height: 120px;
    background: #fff;
  }

  .wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 49px 0;
  }
</style>
