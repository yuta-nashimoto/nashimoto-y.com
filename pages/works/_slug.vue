<template lang="pug">
  .inner
    //- 記事 MV
    WorksHead(
      :title="`${contents[0].title}`" 
      :thumb="`${contents[0].thumb.url}`" 
      :url="`${contents[0].url}`"
    )
    //- 記事 MV

    //- 記事 制作情報
    WorksDetail()
    //- 記事 制作情報

    Btn(
      :outlink="false"
      :btnlink="`/`"
    )
      | 実績一覧
</template>

<script>
import WorksHead from '~/components/works/WorksHead.vue';
import WorksDetail from '~/components/works/WorksDetail.vue';
import Btn from '~/components/Btn.vue';


export default {
  layout: 'Works',
  components: {
    WorksHead,
    WorksDetail,
    Btn,
  },
  async asyncData({ $microcms, params }) {
    const data = await $microcms.get({
      endpoint: 'product/',
      queries: { filters: `slug[equals]${params.slug}` },
    });
    return data;
  },

}
</script>

<style lang="scss" scoped>
.page-enter-active,
.page-leave-active {
  transition: opacity 1s;
}
.page-enter,
.page-leave-active {
  opacity: 0;
}
</style>
