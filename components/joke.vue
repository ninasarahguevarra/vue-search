<template>
  <div>
    <div v-for="joke in jokes" :key="joke.id" class="jokes border-secondary">
      <nuxt-link :to="'jokes/' + joke.id">
        <p>{{ joke.joke }}</p>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Joke',
  // props: {
  //   jokes: {
  //     type: Array,
  //     required: true
  //   }
  // }
  props: ['jokes']
}
</script>

<style lang="sass" scoped>
.jokes
  padding: 15px
  margin-bottom: 15px
  border: 1px solid
  border-radius: 5px
  p
    margin: 0
</style>
