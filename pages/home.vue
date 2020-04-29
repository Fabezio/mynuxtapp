<template lang="pug">
b-container
    main
        h1 Bienvenue!
        p Ce site est dédié aux entreprises et particuliers aux besoins informatiques variés:
        ul
            li développement de sites web, applications web ou mobile
            li mise en place de base de données
            li mise à niveau d'application
            li optimisation de la sécurité
        b-button.btn-block(variant='primary') oui je veux un site optimal

</template>

<script>
export default {}
</script>

<style lang="stylus" scoped>
main
    display block
    max-height 90vh
li
    list-style '=> '
</style>
