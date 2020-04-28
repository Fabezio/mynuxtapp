<template lang="pug">
div.vertical-middle
  b-alert.alert.w-100.py-5(variant="warning" show)
    h1.container.title
      b-icon.mr-3(icon='exclamation-triangle-fill')
      span Oops, cette page n'existe pas!

</template>

<script>
export default {
  layout: 'home',
  data() {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
alert
  width 100%
.title
  font-size 3rem

.vertical-middle
  display flex
  min-height 100vh
  align-items center
</style>
