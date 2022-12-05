<template>
  <div class="container">
    <div class="wrapper">
      <h1>{{ post.title }}</h1>
      <p>{{ post.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'News',

  data() {
    return {
      post: null
    }
  },

  computed: {
    dataNews() {
      return this.$store.state.data
    }
  },

  created() {
    const [date, index] = this.$route.params.slug.split('+')
    const data = this.dataNews.find((item) => {
      return item.date === date
    })
    this.post = data.news[index]
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  height: 100vh;
  margin-top: 20px;

  & h1 {
    font-weight: 700;
    font-size: 18px;
    line-height: 34px;
    color: #000000;
    margin-bottom: 10px;
  }

  & p {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    color: #000000;
  }
}
</style>
