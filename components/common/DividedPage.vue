<template>
  <div class="DividedPage">
    <div class="content">
      <slot name="content" />
    </div>
    <div class="aside">
      <slot name="aside" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'DividedPage'
}
</script>

<style lang="scss" scoped>
.DividedPage {
  display: flex;
  justify-content: space-between;
  align-items: stretch;

  @media screen and (max-width: 992px) {
    flex-direction: column;
  }
}

.aside {
  position: relative;
  flex-shrink: 0;
  flex-grow: 1;
  max-width: 320px;
  width: 320px;

  @media screen and (max-width: 1280px) {
    max-width: none;
    width: 33%;
  }

  @media screen and (max-width: 568px) {
    width: 100%;
    padding-right: 0;
  }
}

.content {
  flex-shrink: 0;
  flex-grow: 1;
  max-width: 768px;
  width: 768px;

  @media screen and (max-width: 1280px) {
    max-width: none;
    width: 66%;
  }

  @media screen and (max-width: 568px) {
    position: relative;
    width: 100%;
  }
}
</style>
