<template lang="pug">

  div
    b-row
      b-col(cols='3')
        b-avatar(rounded='', :src='avatar', size='12em', variant='none' style="position: relative; right: 8px")
      b-col(cols='9')
        h1.display-4.text-left
          | Fabezio, Développeur Web
        h2.subtitle.font-italic.text-left.text-muted
          | Je code pour vous
    nuxt-link.text-light.font-weight-bold(to='/home')
      b-button.my-4.btn-block.font-weight-bold(variant='info' size="lg") ENTRER
    //- br
    //- b-button-group.links
      b-button(variant='primary')
        a.text-light(href='https://nuxtjs.org/', target='_blank')
          | Documentation
      b-button(variant='info')
        a.text-light(:href='ghLink', target='_blank')
          | GitHub

</template>

<script>
// import Logo from '~/components/Logo.vue'

export default {
  layout: 'home',
  components: {
    // Logo
  },
  data() {
    return {
      ghLink: 'https://github.com/Fabezio/mynuxtapp.git',
      avatar: 'avatars/face_co-400px.png'
    }
  }
}
</script>

<style lang="stylus">
.title
  font-family 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif
  display block
  font-weight 300
  font-size 60px
  color #35495e
  letter-spacing 1px

.subtitle
  font-weight 300
  font-size 50px
  color #526488
  word-spacing 5px
  padding-bottom 15px

.links
  padding-top 15px
</style>
