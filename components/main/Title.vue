<template lang="pug">
h1.display-4.mb-4 {{label}}
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: 'Fabezio'
    }
  }
}
</script>
