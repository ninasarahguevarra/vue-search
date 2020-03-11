<template>
  <div>
    <b-container class="py-5">
      <nuxt-link to="/jokes">Back</nuxt-link>
      <h2>{{ joke }}</h2>
      <hr />
      <p>Joke id: {{ $route.params.id }}</p>
    </b-container>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData(context) {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const response = await axios.get(
        `https://icanhazdadjoke.com/j/${context.params.id}`,
        config
      )
      return {
        joke: response.data.joke
      }
    } catch (error) {
      console.log(error)
    }
  },
  head() {
    return {
      title: this.joke,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'joke'
        }
      ]
    }
  }
}
</script>

<style></style>
