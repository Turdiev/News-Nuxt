<template>
  <div class="Publication">
    <div class="Publication__date">
      <span>{{ data.date }}</span>
    </div>
    <template
      v-for="(news, i) in data.news"
    >
      <div
        v-if="i === 4"
        :key="data.date + i"
      >
        <slot name="banner" />
      </div>
      <Card
        :key="i"
        :news="news"
        :index="i"
        :date="data.date"
        class="Publication__card"
      />
    </template>
  </div>
</template>

<script>
import Card from './Card/Card.vue'

export default {
  name: 'PublicationC',

  components: {
    Card
  },

  props: {
    data: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style lang="scss" scoped>
.Publication {
  width: 100%;

  &__date {
    margin-bottom: 20px;

    & span {
      font-weight: 700;
      font-size: 24px;
      line-height: 38px;
      color: #000000;
    }
  }

  &__card {
    margin-bottom: 20px;
  }
}
</style>
