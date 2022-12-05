<template>
  <div
    :class="['Burger', classList]"
    @click="onClick"
  >
    <div class="inner">
      <div />
      <div />
      <div />
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderBurger',

  data() {
    return {
      menuOpened: false
    }
  },

  computed: {
    classList () {
      return {
        ['_opened']: this.menuOpened
      }
    }
  },

  methods: {
    onClick () {
      this.menuOpened = !this.menuOpened
    }
  }
}
</script>

<style lang="scss" scoped>
.Burger {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 23px;
  height: 22px;
}

.inner {
  position: relative;
  width: 100%;
  height: 100%;

  div {
      position: absolute;
      top: 8px;
      left: 50%;
      width: 100%;
      height: 2px;
      background-color: #000;
      transition: all .4s ease;

      &:first-child {
          transform: translate3d(-50%, -10px, 0);
      }

      &:nth-child(2) {
          transform: translate3d(-50%, 0, 0);
      }

      &:last-child {
          transform: translate3d(-50%, 10px, 0);
      }
  }
}

._opened {

  .inner {

      div {

          &:first-child {
              transform: translate3d(-50%, -50%, 0) rotate(45deg);
          }

          &:nth-child(2) {
              opacity: 0;
          }

          &:last-child {
              transform: translate3d(-50%, -50%, 0) rotate(-45deg);
          }
      }
  }
}
</style>
