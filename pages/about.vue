<template>
  <b-container>
    <h1 class="title">About Page</h1>
  </b-container>
</template>

<script>
export default {
  head() {
    return {
      title: 'About Us',
      meta: [
        {
          hid: 'desciption',
          name: 'desciption',
          content: 'this is a sample about content'
        }
      ]
    }
  }
}
</script>

<style></style>
