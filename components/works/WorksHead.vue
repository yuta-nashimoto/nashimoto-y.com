<template lang="pug">
  .works-head.flex.justify-center.mx-auto(class="w-4/5")
    .works-head__thumb.flex-1
      img(:src="thumb")
    .works-head__detail.flex-1
      h2.works-head__detail__ttl(class="")
        | {{title}}
      p.works-head__detail__url
        a(:href="url" target="_blank")
          | {{url}}
      dl.works-head__detail__list
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'サイトタイトル'
    },
    thumb: {
      type: String,
      default: ''
    },
    url: {
      type: String,
      default: ''
    },
  }
}
</script>

<style lang="scss" scoped>

</style>