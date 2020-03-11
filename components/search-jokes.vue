<template>
  <div class="my-3">
    <form @submit.prevent="onSubmit">
      <input v-model="text" type="text" placeholder="Search Jokes..." />
      <input type="submit" value="Search Jokes" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'SearchJoke',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('search-text', this.text)
      this.text = ''
    }
  }
}
</script>

<style></style>
