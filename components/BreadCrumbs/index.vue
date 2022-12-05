<template>
  <div class="BreadCrumbs">
    <nav
      class="nav"
    >
      <ul>
        <template
          v-if="!isMobile"
        >
          <li
            v-for="(item) in items"
            :key="item.name"
            class="nav__item"
            :class="item.classes"
          >
            <n-link
              :to="item.path"
            >
              {{ item.name }}
            </n-link>
          </li>
        </template>
        <template
          v-else
        >
          <li
            class="nav__item"
            :class="items[items.length - 1].classes"
          >
            <div class="backButton"></div>
            <n-link
              :to="items[items.length - 1].path"
            >
              {{ items[items.length - 1].name }}
            </n-link>
          </li>
        </template>
      </ul>
    </nav>
    <div class="underline"></div>
  </div>
</template>

<script>
export default {
  name: 'BreadCrumbs',

  data() {
    return {
      items: [
        { name: 'Главная', path: '/' },
        { name: 'Новости', path: '/', classes: '_active' }
      ]
    }
  },

  computed: {
    isMobile() {
      return window.innerWidth < 568
    }
  }
}
</script>

<style lang="scss" scoped>
.BreadCrumbs {
  margin-top: 22px;
}

.nav {
  margin-bottom: 8px;

  & ul {
    display: flex;
  }

  &__item {
    position: relative;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    display: flex;
    align-items: center;
    color: #5083F3;
    margin-right: 24px;

    &:not(:last-child)::after {
      content: "";
      width: 7px;
      height: 6px;
      border:  solid #000;
      border-width: 1px 0 0 1px;
      transform: translate(-50%, -50%) rotate(130deg);
      position: absolute;
      left: 115%;
      top: 50%;
    }
  }

  & ._active {
    color: #B4C0CF;
  }
}

.backButton {
  position: relative;
  width: 10px;
  margin-right: 10px;
  cursor: pointer;

  &::after {
    content: "";
    width: 12px;
    height: 12px;
    border:  solid #000;
    border-width: 1px 0 0 1px;
    transform: translate(-50%, -50%) rotate(-45deg);
    position: absolute;
    left: 115%;
    top: 50%;
  }
}

.underline {
  width: 90%;
  height: 1px;
  background: #5083F3;
}
</style>
