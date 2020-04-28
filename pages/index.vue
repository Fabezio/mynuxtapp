<template lang="pug">
b-container
  div
    b-row
      b-col(cols='3')
        b-avatar(rounded='', :src='avatar', size='10em', variant='none')
      b-col(cols='9')
        h1.title.text-left
          | Fabezio, Développeur Web
        h2.subtitle.text-left
          | Je code pour vous
    button.btn.btn-lg.btn-warning.my-5
      nuxt-link.text-light.font-weight-bold(to='/home') ENTRER
    .links
      a.button--green(href='https://nuxtjs.org/', target='_blank')
        | Documentation
      a.bg-info.button--grey(:href='ghLink', target='_blank')
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

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
