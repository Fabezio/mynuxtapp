<template lang="pug">
b-form-row.mb-2.mx-0.border.border-2.rounded.rounded-default
    b-col.bg-grey.pr-1.bg-muted.border-right(cols='2')  
        b-icon.mt-2(font-scale='1.25' :icon='icon')
    b-col(cols='10')
        b-form-input.border.border-0( :value='value' @input='updateValue' v-bind='$attrs')
</template>

<script>
export default {
  inheritAttrs: false,
  props: {
    icon: {
      type: String,
      default: ''
    },

    value: {
      type: [String, Number],
      default: ''
    }
  },
  methods: {
    updateValue() {
      this.$emit('input', this.value)
    }
  }
}
</script>

<style lang="stylus" scoped>
.bg-grey
    background #b7b7b7
</style>
