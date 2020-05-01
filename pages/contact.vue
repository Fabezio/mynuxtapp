<template lang="pug">
div
  Title(placeholder='Contactez-moi!')
  form(@submit='checkForm')
    
    Input(type='text' icon='person' value='firstname', placeholder='Nom:')
    Input(type='email' icon='envelope' value='email', placeholder='Email:')
    Input(type='tel' icon='phone' value='phone', placeholder='Téléphone:')
    
    
    b-form-textarea(placeholder='entrez votre message ici' v-model='message')
    //- p.text-info(v-if='message') {{message || 'pas de nom entré'}}
    //- p.text-danger(v-else='') pas de message entré


    b-button-group.btn-block.my-2
      b-button(@click='checkForm' role='submit' variant='warning') Soumettre
      b-button(variant='secondary' role='dismiss') Annuler

  p.text-left(v-if='errors.length') Les éléments suivants sont requis:
    ul
      div(v-for='(error, i) in errors', :key='i')
        li.text-left {{error}}
        


        
</template>

<script>
export default {
  data() {
    return {
      firstname: null,
      email: null,
      phone: null,
      message: null,
      errors: []
    }
  },
  methods: {
    checkForm(e) {
      this.errors = []

      if (!this.firstname) {
        this.errors.push('nom')
      }
      if (!this.email) {
        this.errors.push('adresse email')
      } else if (!this.validEmail(this.email)) {
        this.errors.push('le format de votre email doit être conforme')
      }
      if (!this.phone) {
        this.errors.push('numéro de téléphone')
      }
      if (!this.message) {
        this.errors.push('message')

        if (!this.errors.length) {
          return true
        }

        // this.firstname = null
        // this.email = null
        // this.message = null
        e.preventDefault()
      }
    },
    validEmail(email) {
      const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      return re.test(email)
    }
  }
}
</script>

<style lang="stylus" scoped></style>
