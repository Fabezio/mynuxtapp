<template lang="pug">
div
  b-alert(variant="warning" show)
    h1.container
      b-icon.mr-3(icon='exclamation-triangle-fill')
      span Oops, cette page n'existe pas!

</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
body
  vertical-align middle
</style>
