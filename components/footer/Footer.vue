<template lang="pug">
b-footer.fixed-bottom
  #footer.bg-info.py-2.text-light
    span.font-weight-bold.pr-1 fabezio
    span.pr-1 &copy;
    span.pr-1 {{new Date().getFullYear()}}
    span.font-italic - tous droits réservés
</template>

<script>
export default {}
</script>

<style lang="stylus" scoped>
#footer
  display flex
  justify-content center
</style>
