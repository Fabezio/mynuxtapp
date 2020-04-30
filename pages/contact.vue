<template lang="pug">
div
  Title(label='Contactez-moi!')
  form(@submit='checkForm')
    b-form-input(type='text' v-model='firstname' placeholder='Nom:')
    //- p.text-info(v-if='firstname') {{firstname || 'pas de nom entré'}}
    //- p.text-danger(v-else='') pas de nom entré
    
    b-form-input(type='email' v-model='email' placeholder='Email:')
    //- p.text-info(v-if='email') {{email}}
    //- p.text-danger(v-else='') pas d'email entré
    //- b-form-input(type='text' v-model='firstname' placeholder='Nom:')
    b-form-textarea(placeholder='entrez votre message ici' v-model='message')
    //- p.text-info(v-if='message') {{message || 'pas de nom entré'}}
    //- p.text-danger(v-else='') pas de message entré


    b-button-group.btn-block
      b-button.btn-block(@click='checkForm' role='submit' variant='warning') Soumettre
      b-button.btn-block(variant='secondary') Annuler

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
      message: null,
      errors: []
    }
  },
  methods: {
    checkForm(e) {
      this.errors = []

      if (!this.firstname) {
        this.errors.push('Le nom est requis.')
      }
      if (!this.email) {
        this.errors.push('Votre email est requis.')
      } else if (!this.validEmail(this.email)) {
        this.errors.push('Le format de votre email doit être conforme.')
      }
      if (!this.message) {
        this.errors.push('Le message est requis.')

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
