<template>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-container>
      <b-navbar-brand href="#">DadJokes</b-navbar-brand>
      <ul left>
        <li><nuxt-link to="/">Home</nuxt-link></li>
        <li><nuxt-link to="/jokes">Jokes</nuxt-link></li>
        <li><nuxt-link to="/about">About</nuxt-link></li>
      </ul>
    </b-container>
  </b-navbar>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>
<style lang="sass" scoped>
ul
  margin: 0
  li
    display: inline-block
    padding: 0 15px
    a
      color: white
</style>
