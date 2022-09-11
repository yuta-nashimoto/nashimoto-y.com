<template lang="pug">
  .inner
    h1.text-center(class="lg:text-5xl md:text-4xl")
      | 実績一覧
    ul.product__list.flex.flex-wrap.max-w-screen-xl.mx-auto.mt-10
      Card(
        v-for="(product, index) in contents"
        :title="product.title",
        :lead="product.lead",
        :thumb="product.thumb.url"
        :tags="product.tags",
        :url="product.url",
        :slug="product.slug"
        :key="index"
      )
    p.text-center.mt-20.text-xl 随時更新中
</template>

<script>
import Card from '~/components/Card.vue'

export default {
  layout: 'Default',
  components: {
    Card,
  },
  async asyncData({ $microcms }) {
    const data = await $microcms.get({
      endpoint: 'product',
    });
    return data;
  },

}
</script>

<style lang="scss" scoped>
.product__list {
  justify-content: space-between;
}
</style>
