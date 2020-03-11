<template>
  <b-container class="py-5">
    <h1>Jokes List</h1>
    <SearchJoke @search-text="searchText" />
    <Joke :jokes="jokes" />
  </b-container>
</template>

<script>
import axios from 'axios'
import Joke from '../../components/joke.vue'
import SearchJoke from '../../components/search-jokes.vue'

export default {
  components: {
    Joke,
    SearchJoke
  },
  // async asyncData() {
  //   const response = await axios.get(
  //     'https://jsonplaceholder.typicode.com/posts'
  //   )
  //   return {
  //     jokes: response.data
  //   }
  // },
  // async asyncData() {
  //   const config = {
  //     headers: { Accept: 'application/json' }
  //   }
  //   try {
  //     const response = await axios.get(
  //       'https://icanhazdadjoke.com/search',
  //       config
  //     )
  //     return {
  //       jokes: response.data.results
  //     }
  //   } catch (error) {
  //     console.log(error)
  //   }
  // }
  // async created() {
  //   const config = {
  //     headers: { Accept: 'application/json' }
  //   }
  //   try {
  //     const response = await axios.get(
  //       'https://icanhazdadjoke.com/search',
  //       config
  //     )
  //     this.jokes = response.data.results
  //   } catch (error) {
  //     console.log(error)
  //   }
  // }
  data() {
    return {
      jokes: []
    }
  },
  async created() {
    const config = {
      headers: { Accept: 'application/json' }
    }
    try {
      const response = await axios.get(
        'https://icanhazdadjoke.com/search',
        config
      )
      this.jokes = response.data.results
    } catch (error) {
      console.log(error)
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: { Accept: 'application/json' }
      }
      try {
        const response = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )

        this.jokes = response.data.results
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>

<style></style>
