<template lang="pug">
b-nav-item-dropdown(:text='text', right='' )
  div(v-for='(list, i) in languages', :key='i')
    slot
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: ''
    },
    list: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="stylus" scoped>
// li
//   list-style none
</style>
