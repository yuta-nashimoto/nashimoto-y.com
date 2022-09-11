<template lang="pug">
  li.card-item.rounded.overflow-hidden.shadow-lg
    //- n-link.block.h-full(:to="`/works/${slug}`")
    a.block.h-full(:href="url" target="_blank")
      .overflow-hidden.w-full
        img.transition-transform(v-if="thumb" :src="thumb", alt="サンプル")
        img.transition-transform(v-else src="@/static/product/noimage.png", alt="サンプル")
      .px-6.py-4
        .font-bold.text-xl.mb-2
          | {{title}}
        //- p.text-gray-700.text-base
        //-   | {{lead}}
      .px-6.pt-4.pb-2.mt-auto
        span(v-for="tag in tags").inline-block.bg-gray-200.rounded-full.px-3.py-1.text-sm.font-semibold.text-gray-700.mr-2.mb-2
          | {{tag}}
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Sample Title'
    },
    lead: {
      type: String,
      default: 'テキストが入ります。テキストが入ります。テキストが入ります。テキストが入ります。テキストが入ります。'
    },
    thumb: {
      type: String,
      default: ''
    },
    tags: {
      type: Array,
      default: () => []
    },
    url: {
      type: String,
      default: ''
    },
    slug: {
      type: String,
      default: null
    }
  }
}
</script>

<style lang="scss" scoped>
.card-item {
  width: calc((100% - 40px) / 3);
  &:not(:nth-child(-n+3)) {
    margin-top: 40px;
  }
  & > a {
    &:hover {
      & img {
        transform: scale(1.15);
      }
    }

    & img {
      transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
      transition-duration: 350ms;
    }
  }
}
</style>