<template>
  <n-link
    to="/"
    class="TheLogo _size"
    :class="{_resize: !showLabel}"
  >
    <img
      :src="srcImg"
      alt="logo"
      class="TheLogo__img"
    >
  </n-link>
</template>

<script>
export default {
  name: 'TheLogo',

  props: {
    showLabel: Boolean
  },

  computed: {
    srcImg () {
      return `/images/${this.showLabel ? 'label-' : ''}logo.svg`
    }
  }
}
</script>

<style lang="scss" scoped>
  .TheLogo {
    display: block;
    user-select: none;

    &__img {
      display: block;
      width: 100%;
    }

    &._size {
      width: 302px;
      height: 30px;

      @media screen and (max-width: 568px) {
        width: 160px;
        height: 15px;
      }
    }

    &._resize {
      width: 96px;
      height: 30px;
    }
  }
</style>
