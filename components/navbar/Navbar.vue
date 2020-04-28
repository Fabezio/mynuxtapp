<template lang="pug">
div
  b-navbar(toggleable='lg', type='dark', variant='info')
    b-navbar-brand(href='#') Fabezio
    b-navbar-toggle(target='nav-collapse')
    b-collapse#nav-collapse(is-nav='')
      b-navbar-nav
        b-nav-item(href='#') Menu
        //- b-nav-item(href='#', disabled='') Disabled
      // Right aligned nav items
      b-navbar-nav.ml-auto
        SearchBox
        // cascade langues
        // b-nav-item-dropdown(text='Langues', right='' )
          div(v-for='(lang, i) in languages', :key="i")
            b-icon(:icon="lang.icon")
            b-dropdown-item(:href='lang.href') {{lang.label}}
            //- b-dropdown-item(href='#') ES
            //- b-dropdown-item(href='#') RU
            //- b-dropdown-item(href='#') FA
        b-nav-item-dropdown(right='')
          // Using 'button-content' slot
          template(v-slot:button-content='')
            em Utilisateur
          div(v-for='(button, i) in user', :key="i")
            b-dropdown-item(:href='button.href') {{button.label}}
          //- b-dropdown-item(href='#') Profile
          //- b-dropdown-item(href='#') Sign Out

</template>

<script>
export default {
  data() {
    return {
      languages: [
        { href: '#', label: 'Anglais', icon: 'x' },
        { href: '#', label: 'Espagnol', icon: '' },
        { href: '#', label: 'Français', icon: '' },
        { href: '#', label: 'Allemand', icon: '' }
      ],
      user: [
        { href: '#', label: 'Profil' },
        { href: '#', label: 'Connexion' }
        // { href: '#', label: 'FR' }
        // {href: '#', label='ES'},
      ]
    }
  }
}
</script>

<style lang="stylus" scoped></style>
