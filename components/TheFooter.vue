<template>
  <div class="TheFooter">
    <div class="container">
      <div class="TheFooter__wrapper">
        <TheLogo
          :show-label="false"
          class="TheFooter__logo"
        />
        <nav class="TheFooter__nav">
          <ul>
            <li
              v-for="nav in navigations"
              :key="nav.name"
              class="nav-item"
            >
              <n-link
                :to="nav.path"
              >
                {{ nav.name }}
              </n-link>
            </li>
          </ul>
        </nav>
        <div class="TheFooter__description">
          <span>{{ getDescription }}</span>
        </div>
        <div class="TheFooter__action">
          <div class="TheFooter__action-button">
            <button> <span>Написать нам</span> </button>
          </div>
          <div class="TheFooter__action-social">
            <div
              v-for="item in getSocial"
              :key="item.name"
              class="TheFooter__social-item"
            >
              <n-link
                :to="item.path"
              >
                <img
                  :src="`images/icons-social/${item.name}.png`"
                  alt="logo"
                  class="TheFooter__social-img"
                >
              </n-link>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="TheFooter__sub">
      <div class="TheFooter__sub-copyright">
        <span>сделано &nbsp;&nbsp;в</span>
        <img
          src="images/alente.png"
          alt="logo"
          class="TheFooter__sub-img"
        >
        <img
          src="images/heart-fill.png"
          alt="logo"
          class="TheFooter__sub-img"
        >
      </div>
    </div>
  </div>
</template>

<script>
import TheLogo from './TheLogo.vue'

export default {
  name: 'TheFooter',

  components: {
    TheLogo
  },

  computed: {
    navigations() {
      return this.$store.state.navigation
    },

    getDescription() {
      return this.$store.state.footer.description
    },

    getSocial() {
      return this.$store.state.footer.social
    }
  }
}
</script>

<style lang="scss" scoped>
.TheFooter {
  width: 100%;
  background: #000000;
  padding-top: 52px;

  &__wrapper {
    display: flex;
    justify-content: space-between;
    padding-bottom: 48px;

    @media screen and (max-width: 992px) {
      flex-direction: column;
      align-items: center;
    }
  }

  &__logo {
    @media screen and (max-width: 992px) {
      order: 1;
      margin-bottom: 50px;
    }
  }

  &__nav {
    @media screen and (max-width: 992px) {
      order: 2;
      margin-bottom: 20px;
    }
    & ul {
      @media screen and (max-width: 992px) {
        display: flex;
        flex-direction: column;
        align-items: center;
        order: 2;
      }

      & li {
        width: 208px;
        font-weight: 700;
        font-size: 16px;
        line-height: 20px;
        text-transform: uppercase;
        color: #DCE2EA;

        &:not(:last-child) {
          margin-bottom: 20px;
        }

        @media screen and (max-width: 992px) {
          text-align: center;
        }
      }
    }
  }

  &__description {
    width: 33.5%;

    @media screen and (max-width: 992px) {
      order: 4;
      width: 100%;
      text-align: left;
    }

    & span {
      font-weight: 400;
      font-size: 12px;
      line-height: 20px;
      color: #DCE2EA;
      text-align: left;
    }
  }

  &__action {
    display: flex;
    flex-direction: column;
    align-items: flex-end;

    @media screen and (max-width: 992px) {
      align-items: center;
      order: 3;
    }

    &-button {
      margin-bottom: 72px;

      @media screen and (max-width: 992px) {
        margin-bottom: 40px;
      }

      & button {
        padding: 12px 38px;
        width: 190px;
        height: 50px;
        background: #5083F3;
        border-radius: 8px;

        & span {
          font-weight: 500;
          font-size: 16px;
          line-height: 26px;
          text-align: center;
          color: #FFFFFF;
        }
      }
    }

    &-social {
      display: flex;
      justify-content: flex-end;
      flex-wrap: wrap;
      width: 237px;
      gap: 9px;

      @media screen and (max-width: 992px) {
        justify-content: center;
        margin-bottom: 40px;
      }
    }
  }

  &__social {
    &-item {
      width: 32px;
      height: 32px;
    }

    &-img {
      width: 100%;
      height: 100%;
    }
  }

  &__sub {
    width: 100%;
    height: 52px;
    background: rgba(23, 29, 37, 0.5);

    &-copyright {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100%;

      & span {
        font-weight: 700;
        font-size: 14px;
        line-height: 16px;
        color: #FFFFFF;
        margin-right: 13px;
      }
    }

    &-img {
      &:not(:last-child) {
        margin-right: 13px;
      }
    }
  }
}
</style>
