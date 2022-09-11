<template lang="pug">
  .wrapper
    //- Header
    transition
      nuxt.py-10
    //- Footer
</template>

<script>
import Header from '~/components/common/Header.vue';
import Footer from '~/components/common/Footer.vue';

export default {
  name: 'Default',
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss" scoped>

</style>