<template lang="pug">
  .c-btn.border-2.border-black.w-72.mx-auto
    a.block.text-center.text-xl.duration-150.ease-in(v-if="outlink" target="_blank" class="py-2.5 hover:tracking-extra hover:bg-black hover:text-white")
    n-link.block.text-center.text-xl.duration-150.ease-in(:to="btnlink" v-else class="py-2.5 hover:tracking-extra hover:bg-black hover:text-white")
      span.duration-150.ease-in
        slot
</template>

<script>
export default {
  props: {
    btnlink: {
      type: String,
      defalut: ''
    },
    outlink: {
      type: Boolean,
      defalut: true
    }
  }
}
</script>

<style lang="scss">

.c-btn {
  &:hover {

  }
}
</style>